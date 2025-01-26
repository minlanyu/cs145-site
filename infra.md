# Infrastructure
This page contains helpful information about setting up, completing and submitting problem sets required for CS145. We have divided it into the following sections for your convenience:

- [Infrastructure](#infrastructure)
  - [Installing a virtual machine monitor](#installing-a-virtual-machine-monitor)
    - [MacOS (x86/ARM), Linux and Windows users](#macos-x86arm-linux-and-windows-users)
  - [Setting up the VM environment](#setting-up-the-vm-environment)
    - [Machine guidelines](#machine-guidelines)
    - [Optional: Visual Studio Code Plugin](#optional-visual-studio-code-plugin)
  - [Using GitHub Classroom](#using-github-classroom)
    - [Configure git username and email](#configure-git-username-and-email)
    - [Requesting your project clone](#requesting-your-project-clone)
    - [Clone project contents](#clone-project-contents)
    - [Pull project updates](#pull-project-updates)
    - [Submit the project](#submit-the-project)

We *strongly recommend* you do all problem sets using the virtual machine environment we provide. Before loading our environment, you will need to install a virtual machine monitor.

## Installing a virtual machine monitor

### MacOS (x86/ARM), Linux and Windows users

A virtual machine monitor, or VMM, is a piece of software that allows you to run another operating system "virtually," inside your base operating system. For example, you can run Linux inside Windows.

We have had good experiences with a commercial VMM called [VMWare](https://www.vmware.com/). VMWare's Mac OS X product is called [VMware Fusion](https://www.vmware.com/products/fusion.html), and its Windows product is called [VMWare Workstation](https://www.vmware.com/products/workstation-player.html). These products are not free, but you can get an academic/personal license to use one for the duration of the class.

To obtain VMware: Follow the instructions [here](https://www.mikeroysoft.com/post/download-fusion-ws/).

If you're installing Fusion:

1. Click on the file you downloaded to mount the VMware Fusion icon on your desktop.
2. Click on the VMware Fusion (or VMware Fusion.app) icon in the new window, click Open if prompted, and type your password if prompted. Follow the instructions to install Fusion.

If you're installing Workstation for Windows:

1. Click on the file you downloaded and launch VMware Workstation's installer. If you are asked whether to allow the installer to make changes to your computer, enter your password, and click Yes.
2. A window entitled **Welcome to the VMware Workstation Pro Setup Wizard** should appear. Click Next.
3. When prompted with a license agreement, select I accept the terms in the license agreement, then click Next.
4. You'll next come to a Custom Setup window. You need not change the Install Location. You'll probably want to select **Enhanced Keyboard Driver**, and then select Next.
5. On the next screen, **User Experience Settings**, uncheck the **Help improve VMware Workstation Pro** box and click Next.
6. When prompted about Shortcuts, leave both boxes checked and click Next.
7. You'll now come to the **Ready to install VMware Workstation Pro** screen; select **Install**. It will take a minute or two for the installation.
8. When you come to the Completed the VMware Workstation Pro Setup Wizard screen, click on License, and paste the license key that you got from the VMware store. Then click Finish.

## Setting up the VM environment

We run all our programs in a virtual machine. The VM is built on Ubuntu 22.04.5 and has the P4 and Mininet environment already set up for you. For Project 2 and Project 4 which do not use P4 or Mininet, we *still recommend* you do these projects using this VM.

- **Download the virtual machine we prepared.**
  - For MacOS (x86), Linux and Windows users, the virtual machine files for VMWare can be downloaded [here](https://drive.google.com/file/d/1ilfS0ej46BYVpb-DqW4u9-RxaQgkIc51/view?usp=sharing).
  - For M-series (ARM) Mac users, the virtual machine files for VMWare can be downloaded [here](https://drive.google.com/file/d/1zacRYoIUl6ABbcscxMJxxBidKiTWcULc/view?usp=drive_link).

- **Install the VM.** Directly use your virtual machine software to open the VM file downloaded. The username and the password of this VM are both **p4**. *Note*: The VM file is large. It could consume about 40G disk size in your laptop. Please reserve enough space in your disk before installing the VM. For Windows users, it is recommended to change the VM location to somewhere other than the (default) C Drive.

- **Login to the VM (VMWare).** Right click on the VM in your VM library and select "Connect to SSH".

### Machine guidelines

There are some tasks throughout the projects in this course where you will observe differnet behaviors depending on your machines. In general, if you run the VM on a processor that is equivalent to or better than an i7 with a clockrate higher than 2.8 GHz and at least 8 GB of RAM, you will observe expected behaviors. However, if you get a low-end machine and observe a different behavior for these tasks, it's completely ok. You just need to explain your observations in the report.

We recommend allowing your VM usage of at least two CPU cores and at least 8 GB of RAM (the higher the better, for both). Also, try to turn off the other unnecessary applications in your machines to avoid interrupting the VM.

### Optional: Visual Studio Code Plugin

Just a quick tip if you use Visual Studio Code as a text editor. If you haven't already, you might think about installing the extension: [ms-vscode-remote.remote-ssh](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh). It allows you to open files/directories on your virtual machine in VSCode.

To set it up, you'll need the IP address of your virtual machine which you should be able to find by following the examples here: https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-20-04/.

Combining this with the terminal functionality of VSCode (which will also automatically log into the VM while you're using the plugin above) gives you a great development environment to use for the course!

## Using GitHub Classroom

This course uses git and GitHub Classroom for all its projects. The [Harvard SEAS git introduction](https://wiki.harvard.edu/confluence/display/USERDOCS/Introduction+To+GIT) is a good way to get set up with git quickly. Please take a look at [git notes](http://cs61.seas.harvard.edu/site/ref/git) for the CS 61 Fall 2020 offering for a more interesting introduction. We discuss using GitHub Classroom for our projects here.

### Configure git username and email

```bash
git config --global user.name "FIRST_NAME LAST_NAME"
git config --global user.email "MY_NAME@example.com"
```


### Requesting your project clone

Each project has or will have a GitHub Classroom link posted on our course website. Please click the link *after* you are signed into your github account. This will begin the process of creating a project clone repository for you. You will get an email notification when your cloned repository is accessible.

### Clone project contents

After booting your virtual machine, you need to clone this project repository in your virtual machine (the specific cloning command for each project might be different; please follow project READMEs):

```bash
git clone --recurse-submodules https://github.com/Harvard-CS145/cs145-25-projectX-YYY.git
```

where X (1-8) is the project number, and YYY is your Github username. The description and code skeletons of each minor project are in this repository. In this repository, you will finish your coding in each minor project, test your programs, and submit your codes into Github for grading.


### Pull project updates

When there are changes to the project (announced in Ed), you need to pull latest updates by executing `pull_update.sh` script in the project directory.

```bash
./pull_update.sh
```

### Submit the project

You are expected to tag the version you would like us to grade on using following commands and push it to your own repo. You can learn from [this tutorial](https://git-scm.com/book/en/v2/Git-Basics-Tagging) on how to use git tag command. This command will record the time of your submission for our grading purpose.

```bash
git tag -a submission -m "Final Submission"
git push --tags
```

*Note: Some notes about VMWare were borrowed from the CS 61 offered by Eddie Kohler.*
