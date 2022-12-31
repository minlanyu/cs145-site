# Infrastructure
This page contains helpful information pertaining to setting up, completing and submtting problem sets required for CS-145. We have divided it into the following sections for your convenience:

- [Infrastructure](#infrastructure)
  - [Installing a virtual machine monitor](#installing-a-virtual-machine-monitor)
    - [MacOS (x86), Linux and Windows users](#macos-x86-linux-and-windows-users)
    - [M-series Mac users](#m-series-mac-users)
  - [Setting up the VM environment](#setting-up-the-vm-environment)
    - [Machine guidelines](#machine-guidelines)
    - [Optional: Visual Studio Code Plugin](#optional-visual-studio-code-plugin)
    - [Alternative: Virtual box](#alternative-virtual-box)
  - [Using github classroom](#using-github-classroom)
    - [Requesting your project clone](#requesting-your-project-clone)
    - [Clone project contents](#clone-project-contents)
    - [Submitting the project](#submitting-the-project)

We *strongly recommend* you do all problem sets using the virtual machine environment we provide. Before loading our environment, you will need to install a virtual machine monitor.

## Installing a virtual machine monitor

### MacOS (x86), Linux and Windows users

<p>A virtual machine monitor, or VMM, is a piece of software that allows you to
run another operating system “virtually,” inside your base operating system.
For example, you can run Linux inside Windows.</p>

<p>We have had good experiences with a commercial VMM called <a href="https://www.vmware.com/">VMware</a>. VMware’s
Mac OS X product is called <a href="https://www.vmware.com/products/fusion.html">VMware Fusion</a>, and its Windows product is
called <a href="https://www.vmware.com/products/workstation-player.html">VMware Workstation</a>. These products are not free, but you can get an
academic license to use one for the duration of the class. You can also use a
freely-available VMM, such as Oracle’s <a href="https://www.virtualbox.org/">VirtualBox</a>.</p> 

<p>To obtain VMware:</p>

<ol>
<li><p>Fill out <a href="https://goo.gl/F3z8Sb">this Google form</a> with your name, e-mail,
HUID, etc, requesting the latest version of VMware for your computer
platform (VMware Fusion for Mac OS X, VMware Workstation for Windows, or
(rarely) VMware Workstation for Linux). You will receive an account at the
VMware Software Center once your request is approved. <strong>This step is manual
and it may take up to one business day for you to receive a response.</strong></p>

<p>Your account at the VMware Software Center will have user name and initial
email address both set to your Harvard email address.</p></li>

<li><p>The VMware Software Center is set up like a store. On the “store front”
page, select the latest version of the VMware product you need for your
platform (Fusion or Workstation for Windows). If you see both a free and a
non-free offering of the product, choose the free one.</p></li>

<li><p>Click the Add to Cart button, then proceed through the check-out process
until you reach a screen with a Start Download button. Click the Start
Download button to download the installer.</p></li>

<li><p>On the store front page, click on Your Account/Orders under the Hello,
&lt;your email&gt; menu. Click on View Details to see your Serial Number or
Product Key. You will need that information to run VMware.</p></li>

<li><p>If you’re installing Fusion:</p>

<ol>
<li><p>Click on the file you downloaded to mount the VMware Fusion icon on
your desktop.</p></li>

<li><p>Click on the VMware Fusion (or VMware Fusion.app) icon in the new
window, click Open if prompted, and type your password if prompted.
Follow the instructions to install Fusion. When prompted for a license
key, use the serial number generated for you by the VMware Software
Center.</p></li>
</ol>

<p>If you’re installing Workstation for Windows:</p>

<ol>
<li>Click on the file you downloaded and launch VMware Workstation’s
installer. If you are asked whether to allow the installer to make
changes to your computer, enter your password, and click Yes.</li>
<li>A window entitled <strong>Welcome to the VMware Workstation Pro Setup
Wizard</strong> should appear. Click Next.</li>
<li>When prompted with a license agreement, select I accept the terms in
the license agreement, then click Next.</li>
<li>You'll next come to a Custom Setup window. You need not change the
Install Location. You'll probably want to select <strong>Enhanced Keyboard
Driver</strong>, and then select Next.</li>
<li>On the next screen, <strong>User Experience Settings</strong> uncheck the <strong>Help
improve VMware Workstation Pro</strong> box and click Next.</li>
<li>When prompted about Shortcuts, leave both boxes checked and click
Next.</li>
<li>You'll now come to the <strong>Ready to install VMware Workstation Pro</strong>
screen; select <strong>Install</strong>. It will take a minute or two for the
installation.</li>
<li>When you come to the Completed the VMware Workstation Pro Setup
Wizard screen, click on License, and paste the license key that you
got from the VMware store. Then click Finish.</li>
</ol></li>
</ol>

### M-series Mac users

For M-series Mac users, unfortunately the solutions above do not support your M-series due to the difference in architecture. We recommend [UTM](https://mac.getutm.app/), an open-source free VMM that supports M-series.


## Setting up the VM environment

We run all our programs in a virtual machine. The VM has the P4 and Mininet environment already set up for you. For project2 and project4 which do not use P4 or Mininet, we *still recommend* you do these projects using this VM. 

- **Download the virtual machine we prepared**. 
  - For MacOS (x86), Linux and Windows users, the virtual machine files for VMWare can be downloaded at [VMWare VM](https://drive.google.com/file/d/1ed-EArBHGze3v-8OllzXlY7az03jt4yo/view?usp=sharing). 
  - For M-series Mac users, the virtual machine files for UTM can be downloaded at [UTM VM](https://drive.google.com/file/d/16ZIQztUSUFaPVi9vZf9QycPnIDWfoKOZ/view?usp=sharing). 

- **Install the VM.** Directly use your virtual machine software to open the VM file downloaded. The username and the password of this VM are both **p4**.
  *Note*: The VM file is large. It could consume about 40G disk size in your laptop. Please reserve enough space in your disk before installing the VM.
 
- **Login to the VM (VMWare).** right click on the VM in your VM library and select "Connect to SSH".

### Machine guidelines
There are some tasks throughout the projects in this course where you will observe differnet behaviors depending on your machines. In general, if you run the VM on a processor that is equivalent to or better than an i7 with a clockrate higher than 2.8 GHz and at least 8 GB of RAM, you will observe expected behaviors. However, if you get a low-end machine and observe a different behavior for these tasks, it's completely ok. You just need to explain your observations in the report. 

We recommend allowing your VM usage of at least two CPU cores and at least 8 GB of RAM (the higher the better, for both). Also, try to turn off the other unnecessary applications in your machines to avoid interrupting the VM. 

### Optional: Visual Studio Code Plugin

Just a quick tip if you use Visual Studio Code as a text editor. If you haven't already, you might think about installing the extension: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh. It allows you to open files/directories on your virtual machine in VSCode.

To set it up, you'll need the IP address of your virtual machine which you should be able to find by following the examples here: https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-20-04/.

Combining this with the terminal functionality of VSCode (which will also automatically log into the VM while you're using the plugin above) gives you a great development environment to use for the course!

### Alternative: Virtual box
While the recommended virtual achine monitor for our course is VMWare, our projects work without issues on Virtual Box as well. We can provide a Virtual Box VM on request. Here are some helpful notes in case you prefer Virtual Box.

- For SSH access: Usually it is hard to use the virtual machine directly through your hypervisor. We have installed OpenSSH server in this virtual machine so that you can use it through ssh command. You can connect to your virtual machine by typing:  `ssh p4@localhost -p 1338`

- Saving disk space: as you work on your VM for extended periods of time, you might notice a disk overhead larger than the files you added to your VM. We encourage taking steps to reduce virtual disk size after completing each project in case you are on a machine that does not have a lot of disk space. You can use [this post](https://superuser.com/a/529183) as a helpful guideline for reducing your virtual disk size.

Note that VirtualBox currently does not support M-series Macbook.
## Using github classroom

This course uses git and github classroom for all its projects. The [Harvard SEAS git introduction](https://wiki.harvard.edu/confluence/display/USERDOCS/Introduction+To+GIT) is a good way to get set up with git quickly. Please take a look at [git notes](http://cs61.seas.harvard.edu/site/ref/git) for the CS 61 Fall 2020 offering for a more interesting introduction. We discuss using github classroom for our projects here.

### Requesting your project clone
Each project has or will have a github classroom link posted on our course website. Please click the link *after* you are signed into your github account. This will begin the process of creating a project clone repository for you. You will get an email notification when your cloned repository is accessible.

### Clone project contents

After booting your virtual machine, you need to clone this project repository in your virtual machine

```
git clone https://github.com/Harvard-CS145/projectX-YYY.git
```

where X (1-8) is the project number, and YYY is your Github username. The description and code skeletons of each minor project are in this repository. In this repository, you will finish your coding in each minor project, test your programs, and submit your codes into Github for grading.

### Submitting the project
Simply commiting and pushing all changes to the main branch of your cloned project repository counts as a submission. We will consider the *most recent commit prior to the project deadline* as your final submission. In the case of extensions, please leave a note *Not ready for grading* on your commited repo, and mark your final submission as *Ready for grading*. We will count late hours accordingly.

<p><i>Note: Some notes about VMWare were borrowed from the CS 61 offered by Eddie Kohler.</i></p>
