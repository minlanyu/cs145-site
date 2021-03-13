# Load balancing project

## Objectives
- Implement software load balancers
- Use VIP and IPinIP to deliver traffic
- Understand the benefit of Direct Server Return(DSR)

## Overview
Software load balancers distribute connections among various servers in order to have more efficient use of the number of servers. To the client, all traffic is sent and received from one IP address. However, since the IP address does not belong to any one machine, but belongs to the system of servers and load balancers, it is called a Virtual IP(VIP).

Packets are sent to the Load Balancers, then the packets are forwarded to servers, where a response is formed and sent to the client. The message from the server can be sent either going through the Load Balancer, or directly to the client. One benefit of Direct Server Return is that it avoids the load balancer as a bottleneck, as responses from the server are generally larger than the requests from the client.

Disclaimer: Since the software load balancer is going to be implemented using scapy on layer 7, the load balancer doesn't improve performance in our case.

To learn more about load balancing, please take a look at [Ananta](https://dl.acm.org/citation.cfm?id=2486026).


## Getting Started
In this project, we will be implementing a software load balancer using [scapy](https://scapy.readthedocs.io/en/latest/), a packet parsing package in python.
To install scapy, run `pip install scapy` in the terminal.

## Topology
As usual, we will use the fattree topology for this project.
![fattree_topo](./figures/fattree_labelled.png)

## Dataplane Code
Copy your p4 code from the ECMP Routing Project. This code does not need to be changed for this project.

## Routing Controller
Provided to you under `routing-controller.py` is some controller code. This routing controller code currently should be able to write ecmp routing rules for networks of switches running ECMP p4 code. You can test this you by changing up the topology and running the same controller code. The `pingall` command should work.

For this project, we will be modifying the `route` function of `routing-controller.py`. Since we need to support a VIP in our network, we have to modify our controller to support routing to the Virtual IP. For this project, we will use 20.0.0.1 as our VIP, and our load balancers will be on h1 and h2.

The routing controller code should be modified so that any packet with destination IP as the VIP is routed to the load balancers.

Tips for implementation of a routing controller for this load balancing system.
- On switches other than `t1` (the one right before h1 and h2), the packets that are destined to the VIP should be routed as if they are going to h1 or h2.
- At `t1`, you should use the ECMP rules to split up packets destined for 20.0.0.1 between the two load balancers

Some useful documentation for this part of the project is given under this link: https://github.com/nsg-ethz/p4-utils#topology-object

### Testing the Routing Controller
#### Test 1
```
sudo p4run --conf fat_tree_one_pod_app.json
```
then run `pingall` in mininet. If all pings go through, then your routing should work for normal packet routing.
#### Test 2
run
```bash
sudo tcpdump -enn -i t1-eth1
```
and
```bash
sudo tcpdump -enn -i t1-eth2
```
so we can monitor the packets going to h1(through t1-eth1) and the packets going to h2(through t1-eth2).
Now if you run
```
mininet>h5 ping 20.0.0.1
```
then you should see only packets going to one of the load balancers. If you run ping from another host, the load balancer that receives the packet may change. Try to ping from different hosts to verify that your switches are dividing the flows amoung the two load balancers correctly. The load balancer should not be replying to the ping, so don't worry if the ping fails. As long as you see the packets on the tcpdump, then the routing controller is working properly. 

If you see that packets being destined to 20.0.0.1 are being delivered to h1 or h2, then your routing controller should work.

## Load Balancer
The load balancer needs to:
1. receive packets
2. encapsulates packets with another IP header
3. select the server(`h13`, `h14`, `h15`, or `h16`) to send to based on a hash of the five tuple
4. set the destination IP to be the server's IP
5. send the packet

In this section, we will be working with `load_balancer.py`. All of your changes should be made within this file.

### Sniffing Packets
This section will show you how to read(sniff) packets with scapy

First, we need to import scapy with
``` python
from scapy.all import *
```

To read the incoming packets, we will use the `sniff` function in the scapy package.
This function sniffs for packets and sends them to the function that we pass in the `prn` argument.
We can also add a `filter` argument that can filter packets before passing them into the function.
The filter uses Berkeley Packet Filter(BPF) syntax. Here is the link to some documentation about BPF: https://biot.com/capstats/bpf.html

For example,
``` python
sniff(filter="tcp and dst host 10.1.2.1", prn=do_something)
```
will sniff for packets that use the TCP protocol, and are destined for the IP 10.1.2.1. Then, the packet will be passed into the `do_something` function that we define.

In our case, we need to sniff for TCP packets going to 20.0.0.1.

After you use the sniff function, the meat of the load balancing code will be in the function that the packets are sent to(`do_something`).
Your `do_something` function should have one input parameter called `packet`.

### Forging packets
In order to send the packet to the server, we have to encapsulate the received packet with scapy.

We will encapsulate the packet with IPinIP.
The IPinIP protocol is when you have an IP packet that is encapsulated by another IP header. Thus, the inner packet will be routed based on the outer header, but the information in the inner header will stay the same. The IPinIP protocol is important for DSR, because it gives the server access to the client IP address and the client port.

Here is an example of how to forge a TCP packet with scapy:

```python
packet = Ether() / IP(dst="10.1.2.1") / TCP(sport=333, dport=222)
```
In this case, we want to do IPinIP encapsulation, so you can add on an extra IP header on top of the sniffed packet.

If you want to debug and print out what your packets look like, just use
```python
packet.show() # show packet before computing checksums, etc.
```
 or
```python
packet.show2() # show packet after computing checksums, etc.
```

Specify the destination MAC address to be the closest switch. After you have created your packet, send it with the `sendp` function, which sends the packet at layer 2. 

<!-- sending with `send` to the server doesn't work with scapy, but sendp works. perhaps something to do with IPinIP. when you use `send` command, scapy automatically does ARP and adds an Ether header to it. -->

### Parsing Packets
In order to forge and encapsulate your packets, you will have to do some parsing on the sniffed packets.

Packet headers in scapy are formed of layers. To access these layers, do
```
packet[Ether]
```
Each layer contains all layers after it, for example, `packet[Ether]` includes the IP header, the TCP header, and the data payload. 

Another way to traverse up the header layers is to use `.payload`. For example,
```
packet[IP].payload
```
accesses the TCP header for TCP packets. This is useful when parsing IPinIP headers, as there are two IP headers, and `packet[IP]` will only return the first IP header.

### Hashing
We need to hash each packet's five tuple in order for the load balancer to determine which server to send the packet to.

To hash the five-tuple, you can use any hash function. If you want to consider performance, then you can also use bitwise operators as your hash function.

One option is to use zlib in python. After importing, you can run: `zlib.crc32(bytes(five_tuple)) & 0xffffffff` to hash the five tuple.

### Testing the Load Balancer

In mininet, run:
```
mininet> xterm hW hX hY hZ
```
where W,X,Y,and Z are the host numbers where you are going to send packets to. For testing purposes, you may find it helpful to not do hashing in your load balancing code and only send to one designated host(for example `h16`).

And on each of the external terminals of the servers(`hW hX hY hZ`), run the command
```
sudo tcpdump -enn 
```
so we can monitor the packets arriving at each server hosts.

Now, if you run
```
mininet>h3 ping 20.0.0.1
```
then you should see packets arriving at the servers being printed out on the terminal.

At this point, packets are being sent from the clients and routed to the load balancers, where they are encapsulated and delivered to the servers. The final step is to decapsulate and have a server handle the packets.

## Host Agent
 - decapsulate the IPinIP packet
 - send to server

In this section, we will work main on the file: `agent.py`. However, we have to do some setup before we run the host agent.

The server in our case will be a built in php webserver. This server is run using: `php -S 20.0.0.1:80 -t ~/resources/wwwroot`

The host agent's job is to decapsulate the IPinIP packets before sending it to the server. The host agent will be run on the same machine as the server(i.e. the host agent will be a python script running on the same host that the server is running on). 

After decapsulation, the destination IP of the packet should be the VIP. In order for this packet to be properly routed to the server, we need to add the VIP to a local interface. This way, the server machine believes that 20.0.0.1 is one of its own IP addresses and it will route the packet to itself instead of back to the load balancers.

### Adding VIP to Interface
We must have the server machine believe recognize the VIP as it's own IP address, so that it does not push the packets from the host agents back into the network.

We can add the IP address to an interface with the `ip addr add` in the terminal of the host. Since we want to add to the eth0 interface, we will specify that `dev hX-eth0`(with X being the host number). The command should look something like this: `ip address add IFADDR dev STRING`. There is a script called `set_up_servers.sh` that will run these commands on the specified hosts. 

When we run the server, it will bind to the VIP address. This means that it will be able to accept these decapsulated packets, and also reply with the proper source IP address. If the server is bound the the host's IP address, and not the VIP address, then the reply will not be accepted by the client, as the source was not the IP address that the client originally sent the packet to.

Servers, and also the host agent scripts, will be run on `h13`, `h14`, `h15`, and `h16`.

### Decapsulation and Delivery

Receiving the packets should be the same as the load balancer(i.e. with `sniff`). In order to decapsulate, you can use scapy packet parsing.
Sending packets can be done with `send`. You also need to run `conf.L3socket=L3RawSocket` in your python code in order to speak to local applications. The loopback interface is special, so when sending packets to your own machine(like we are doing here) requires you to build packets one layer upper.


## Testing
Remember to run `sudo service lightdm start` to have a GUI.

1. run `xterm` to open an external terminal for the load balancers, clients and servers(you can open many terminals with 1 command through something like this `xterm h1 h2 h16`)
 1a. for each server, open 2 terminals
2. On the load balancers(`h1` and `h2`), run `python load_balancer.py`
3. On the server hosts(`h13`, `h14`, `h15`, `h16`), run `agent.py`
4. Run `php -S 20.0.0.1:80 -t ~/resources/wwwroot` on every server host(`h13`, `h14`, `h15`, `h16`).
5. Run `wget 20.0.0.1` on each client.

<!--- sending IPinIP packets from the LB to the server results in ICMP packets(destination unreachable, protocol unreachable) to be sent back to the load balancer. This doesn't affect performance. It may be solved by adding an IPinIP tunnel.
There is also sometimes a bug where pinging or sending packets to the VIP results in ttl exceeded because of a routing loop at the LB.-->

## Extra Credit(10)

Make a visualization(a graph or flow chart) of what the packets look like as they traverse through your system. This graph could show how many/what headers are on your packet as it passes through each element of the system(the client, the load balancer, the host agent, etc.). You could also draw arrows to diagram how packets are routed according to this load balancing system. 

Remember to embed your graph or flow chart in your `report.md`. 

## Additional Food For Thought
Here are some questions that you may want to talk about in your report for further discussion. This is optional though. These questions are mostly for you to further your knowledge about the challenges that come with developing load balancers. 

How could a constantly changing Destination IP pool(constant server pool updates) make the load balancing system more complicated?  What are some ways in which load balancers can handle DIP pool updates seamlessly? What are some possible ways you could handle scaling out software load balancers?

How could you implement a load balancer with P4 on a programmable switch? What tables or registers would you need? How could you deal with DIP pool updates on a switch? 
In Silkroad, the authors implemented a working load balancer with P4 on a switch. Here is the link to the paper if you are interested: https://dl.acm.org/doi/pdf/10.1145/3098822.3098824 

## Submission and Grading

### What to Submit

You are expected to submit the following documents:

1. Code: 
   a. Routing controller code (`routing-controller.py`)
   b. Load balancer code (`load_balancer.py`)
   c. Host agent code (`agent.py`)
2. report/report.md: Describe how you implemented the load balancer in `report.md`. Also optionally include your responses to the extra credit section. 

### Grading

The total number of points is 100:

- 30: For your description of how your load balancing system works in `report.md` and the extra credit.
- 30: routing controller code
    - criteria: `pingall` should run smoothly, packets to VIP should be routed to `h1` and `h2` and split evenly among the two 
- 20: load balancing code.
    - criteria: sniff packets destined to the VIP, encapsulate packets with IPinIP, route packets based on a hash of the 5 tuple
- 20: host agent code/functionality of the whole system.
    - criteria: sniff packets destined for the server, decapsulate IPinIP packets, forward onto the server, wget succeeds
- 10: Extra credit: visualization of the load balancing system
- Deductions based on late policies

## Survey

Please fill up the survey when you finish your project.

[Survey link](https://docs.google.com/forms/d/e/1FAIpQLSc6aRw61glVqicOhQRjO4ZIoawQ0IOq6-eqANOadsQHyFlrrg/viewform?usp=sf_link)
