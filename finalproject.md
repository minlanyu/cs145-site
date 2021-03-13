# Project 7: Final Project

You are supposed to design and implement an open-ended project. You can choose between three directions. Check with us about your project ideas to make sure they’re in scope. Think big!

## Direction 1:
We have built a data center network in the past projects. Now you are supposed to add a new feature to it. Interesting projects may become course projects for future semesters. One example is the [P4 Network Visualizer](https://github.com/Danieltech99/P4-Network-Visualizer). 

In general, you can look for project ideas by revisiting the key ideas discussed in lectures and pick one idea to implement. 
Here are a few suggested topics. 

### Running spanning tree protocol and learning switches in Mininet

### Porting link-state or distance vector protocols to FatTree setting in Mininet
Our link-state and distance vector implementation in project 2 is a standalone program. Can you try porting it to the Mininet setting so that we can run it in the data center networks we construct?

### Running BGP in Mininet
[Quagga](https://www.quagga.net/) would be a useful starting point. 

### Running DCTCP in Mininet and compare its performance with TCP

### Implement MPLS or WCMP in Mininet

### Add P4 debugging tools
Build an innovative and useful tool that can help P4 developers visualize, identify or better understand their program's behavior and more conveniently debug it.

### Add more testing cases 
Many of our course projects can be improved with better automatic testing cases. Propose some testing scripts that would automatically catch problems in students' codes.

## Direction 2:
Another option is to read papers in networking and try to reproduce some results (see the [Stanford course blog](https://reproducingnetworkresearch.wordpress.com/) for examples).

## Direction 3: Software load balancing
If you prefer projects with detailed instructions, you can also try out the [Software load balancing project](LoadBalancing.md). In addition to following the instructions, you should be creative in adding new features to the projects or compare the tradeoffs for different implementation alternatives. 

For example, you may consider migrate software load balancers to part of P4 switches. See the [reference paper](http://minlanyu.seas.harvard.edu/writeup/sigcomm17.pdf). 

## Direction 4: Test network usage of an application in the cloud

You can choose one application and one cloud platform, run your applications there, measure the network usage (delay, throughput, changes, etc.), and use the knowledge you learnt from this class to explore new observations and discuss potential improvements.

Note that, for better or worse, this is an interesting time to measure cloud network usage considering the public health situation has lead to unparalleled network traffic for remote work and communication.

### Example applications
In the past, students have chosen applications such as machine learning, web services, video streaming, or simply iperf. 

### Example platforms
In the past, students have chosen GPU/TPU, serverless (lambdas), various cloud instances, across data center regions, etc in Google cloud, Microsoft Azure, and Amazon EC2.

## Submission requirements 
In addition to the code, write up your project in a file that you add to your repository. Your writeup should answer these questions:

- What was your goal?
- What’s your design?
- What code did you write (what files and functions)?
- What challenges did you encounter?
- How can we test your work?
- The writeup need not be very long; 300 words can do it if you use the words well.


<!--
### Inband Network Telemetry (INT)
Telemetry we used in this course so far usually is based off of transfering data to the control plane in some way, for example, writing to registers and having controllers read the registers. This often has a large overhead and is slow.
Inbad Network Telemetry(INT) is a way to monitor and observe network events. INT operates entirely in the dataplane, allowing data to be transfered faster and at a higher granularity.
INT works by writing data that needs to be monitored into the packet header in the p4 code. The receiver host then parses the data out of the packet header, allowing for more visualization or analysis. Parsing the packet header can be done through something like [scapy](https://scapy.readthedocs.io/en/latest/).
#### Resources
[INT p4 video](https://www.youtube.com/watch?v=FOOL5BeHNVY)
[INT spec](https://p4.org/assets/INT-current-spec.pdf)
[Multi-Hop Route Inspection (MRI)](https://github.com/p4lang/tutorials/tree/master/exercises/mri)
This is a scaled down version of INT. Does not work for larger amounts of hops, as ipv4 headers have a max length because of the ihl field.
-->
