# CS 145, Spring 2020: Cloud Networking and Computing

## Overview

Clouds have become critical infrastructures for many applications in business and society (e.g., social media, public health, and entertainment). In this course, we will take a look inside the cloud infrastructure and learn critical technology trends and challenges in the networking and computing layers. We will discuss the design choices of performance, scalability, manageability, and cost in various cloud companies such as Amazon, Google, Microsoft, and Facebook. This course includes lectures and system programming projects.

- Instructor: Minlan Yu (MD 137)
- Lecture time: MW 1:30pm-2:45pm
- Location: TBD
- Office hour: M 12:30-1:30, MD 137
- Discussion list: [Piazza](https://piazza.com/class/jy80ngwm9123)
- Prerequisite: There are no official prerequisites. Recommended prep: system programming at the level of CS 61 or CS 143.


## Textbook
- This course covers both basic networking concepts and advanced cloud networking concepts.
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find [an online version](https://proquest-safaribooksonline-com.ezp-prod1.hul.harvard.edu/9780123850591) in Harvard library.
- There are no good textbook for cloud related concepts. You have to refer to my slides and the papers listed in the syllabus for readings. Please contact me if some concepts are hard to understand and I'll provide more supplemental materials.

## Coursework
- Class and biweekly section participation is mandatory.
- Extra credits given based on your contributions to in-class and piazza discussions.
- Programming projects: 65%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Midterm exam: 20%
- In-class and in-piazza participation 5%
- Scribe: 5%
- In-class news presentation: 5%

## Syllabus

| Weeks        | Mon                                                                                                                                                                                                | Tue  | Wed                                                           | Thu                                    | Fri                                         | Sat  | Sun                   |
| :----------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--- | :------------------------------------------------------------ | :------------------------------------- | :------------------------------------------ | :--- | :-------------------- |
| **Jan 27-Feb 2** | Course Overview <br> introduction of clouds | | Cloud applications I (scalability, low latency) `Scribe`         |     Project 1 released <br> (Setup)| |
| **Feb 3-9**      | Cloud applications II (bandwidth, reliability)`Scribe`                                                                                                                                                     |      |  Cloud applications III (perf isolation)`Scribe`   |                                        |     Mininet and P4 tutorial                                        | | Project 1 due
| **Feb 10-16**    | L2/L3                                                                                  |      | Data center topology`Scribe` |   Project 2 released <br> (Topology )          |                      | | 
| **Feb 17-23**    | No class <br> (President's Day) |      | Discovery   |                   |P4 tutorial continued; topology|      | Project 2 Due |
| **Feb 24-Mar 1** |  Routing basics   |      | Tutorial: ECMP; failure events                                                              | Project 3 Released <br> (Routing, ECMP)                    |  |      |          |
| **Mar 2-8**      |     Data Center routing`Scribe`                             |      |     BGP Routing <br> data center BGP routing`Scribe`                       | project 4 released (Measurement) |  Measurement and debugging tools|      | Project 3 due         |
| **Mar 9-15**     |   Transport layer and TCP basics <br> *K&R 3.1-3.5*          |      |  Congestion control and fairness  <br> *K&R 3.6-3.7*                                                               | project 5 released (Failure recovery & ARP)                     |                                             |      |        |
| **Mar 16-22**    | no class (Spring recess)                                                                                                                                                                           |      |                                                               |                                        |                                             |      |       Project 4 due                  |
| **Mar 23-29**    |   Data Center TCP`Scribe`                                                                         |      | Traffic engineering basics, WCMP, CONGA`Scribe`                                                             | project 6  released <br> (Flowlet)                    |   [CONGA](https://people.csail.mit.edu/alizadeh/papers/conga-sigcomm14.pdf) details                                        |      | Project 5 due         |
| **Mar 30-Apr 5** |  Course review  |      |  network functions`Scribe`                                             | project 7  released  <br> (CONGA)                   |                                             |        | project 6  due        |
| **Apr 6-12**     |   Exam                          |      |                            Load balancing  `Scribe`                                  |  |  [Ananta](https://conferences.sigcomm.org/sigcomm/2013/papers/sigcomm/p207.pdf) Details                                       |   | |
| **Apr 13-19**    |      Switches and P4`Scribe`                                                                                                                                                                 |      | Software defined networking`Scribe`                                    |     project 8  released  <br> (SLB)                                   |                                             |    |  project 7  due|
| **Apr 20-26**    |       WAN (wide-area networking) `Scribe`                                                                                                                                                                                            |      | Microsoft Guest Lecture                                       |                                      |                                       Final project suggestions       | | |
| **Apr 27-May 3** | Security and Ethics  |      |        Course Summary                                                       |                          |                                             |     |  project 8  due    |
| **May 4-10**     |                                                                                                                                                                                                    |      |                                                               |                                        |                                     Final project proposal due         |      |                      |
| **May 11-17**    |                                                                                                                                                                                                    |      |                                                               |                                        | Final project due                           |      |                       |




## Project
During this course, we will build a complete datacenter network. To better understand the skills you will be learning as part of the course, take a look at the first assignment [here](https://classroom.github.com/a/mRCEAfN8). 

## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)


## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)
