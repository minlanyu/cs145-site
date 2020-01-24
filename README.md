# CS 145, Spring 2020: Networking at Scale

## Overview

Modern networks have grown to extremely large scale (connecting millions of servers) and high speed (with Terabits per second) to meet the needs of a variety of cloud applications in business and society (e.g., social media, public health, and entertainment). In this course, we will study not only basic concepts in networking but also how these concepts get applied and extended for networking at scale. We will discuss the recent technology trends and design choices of performance, scalability, manageability, and cost faced by companies who own large-scale networks such as Amazon, Google, Microsoft, and Facebook. This course includes lectures and system programming projects.

- Instructor: Minlan Yu (MD 137)
- Lecture time: MW 1:30pm-2:45pm
- Location: TBD
- Office hour: W 12:30-1:30, MD 137
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
- Midterm exam: 15%
- Scribe: 5%
  - Because there's no good textbook on cloud networking, we plan to create and iterate on a set of course notes that we can reuse in future years. Each student is expected to scribe one lecture. 
- In-class and in-piazza participations 10%
  - including a few cloud news presentations.
- Please refer to the first lecture slides for details.


## Syllabus

| Weeks        | Mon                                                                                                                                                                                                | Tue  | Wed                                                           | Thu                                    | Fri                                         | Sat  | Sun                   |
| :----------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--- | :------------------------------------------------------------ | :------------------------------------- | :------------------------------------------ | :--- | :-------------------- |
| **Jan 27-Feb 2** | Course Overview <br> introduction of clouds | | Cloud applications I (scalability, low latency) `Scribe`         |     Project 1 released <br> (Setup)| |
| **Feb 3-9**      | Cloud applications II (bandwidth, reliability)`Scribe`                                                                                                                                                     |      |  Cloud applications III (perf isolation)`Scribe`   |                                        |     Mininet and P4 tutorial,                                        | | 
| **Feb 10-16**    | L2/L3 (K&R 4.1-4.3, 6.1-6.3)                                                                                 |      | Data center topology (K&R 6.6)`Scribe` |   Project 2 released <br> (Topology)          |                      | | Project 1 due
| **Feb 17-23**    | No class <br> (President's Day) |      | Discovery (K&R 6.4, 6.7)   |    Project 3 Released <br> (Routing, ECMP)                ||      | Project 2 Due |
| **Feb 24-Mar 1** |  P4 tutorial continued; topology; ECMP   |      | Tutorial: Measurement and debugging tools          |          project 4 released (Measurement)          |  |      |     Project 3 due
| **Mar 2-8**      |     Routing basics (K&R 5.2, 5.3, 6.4)                            |      |    Data Center routing`Scribe`                         |project 5 released (Failure recovery & ARP)  | failures, ARP, flowlet  |      |        Project 4 due
| **Mar 9-15**     |  BGP Routing <br> data center BGP routing (K&R 5.4)`Scribe`          |      |  Transport layer and TCP basics <br> *K&R 3.1-3.5*                                                                |     project 6  released <br> (Flowlet)                  |                                             |      |     Project 5 due 
| **Mar 16-22**    | no class (Spring recess)                                                                                                                                                                           |      |                                                               |                                        |                                             |      |                         |
| **Mar 23-29**    |  Congestion control and fairness  <br> *K&R 3.6, 3.7.1*                                                                         |      | Data Center TCP (K&R 3.7.2)`Scribe`                                                              |      project 7  released  <br> (CONGA)              |                             [CONGA](https://people.csail.mit.edu/alizadeh/papers/conga-sigcomm14.pdf) details              |      |    project 6  due
| **Mar 30-Apr 5** |  Course review  |      |  Traffic engineering basics, WCMP, CONGA`Scribe`                                            |                    |                                             |        |         |
| **Apr 6-12**     |   Exam                          |      |      network function and Load balancing  `Scribe`                                  |  project 8  released  <br> (SLB)  |  [Ananta](https://conferences.sigcomm.org/sigcomm/2013/papers/sigcomm/p207.pdf) Details                                       |   | project 7  due
| **Apr 13-19**    |      Switches and P4`Scribe`                                                                                                                                                                 |      | Software defined networking(K&R4.4, 5.5)`Scribe`                                    |                                      |                                             |    |  |
| **Apr 20-26**    |       WAN (wide-area networking) `Scribe`                                                                                                                                                                                            |      | Microsoft Guest Lecture                                       |                                      |                                       Final project suggestions       | | project 8  due
| **Apr 27-May 3** | Security and Ethics  |      |        Course Summary                                                       |                          |             Final project proposal due                                 |     |      |
| **May 4-10**     |                                                                                                                                                                                                    |      |                                                               |                                        |                                             |      |                      |
| **May 11-17**    |                                                                                                                                                                                                    |      |                                                               |                                        | Final project due                           |      |                       |


<!-- *skim [Jupiter](http://conferences.sigcomm.org/sigcomm/2015/pdf/papers/p183.pdf)*                                    -->

## Project

### Objectives

This course project runs throughout the semester. Through this project you will reach two objectives

* Build a full stack data center network on your own laptop ranging from topology, routing, to applications.
* You will get hands-on experiences of the major concepts learnt in lectures and understand the tradeoffs of different design decisions

### First project
You can also try out the first assignment [here](https://classroom.github.com/a/mRCEAfN8). 

### Late policy
You should submit your work on an assignment (electronically) before its due time. All assignments will be due at 11:59pm on their selected days. 

If you submit your work late, we will award you a fraction of the score you would have earned on the assignments had it been turned in on time, according to this sliding scale:

* 90% for work submitted up to 24 hours late
* 80% for work submitted up to 2 days late
* 70% for work submitted up to 3 days late
* 60% for work submitted up to 5 days late
* 50% for work submitted after 5 days late

For example, if you should have earned 8/10 points but submitted 36 hours late, you will instead earn 6.4 points.

That said, you are allowed **SIX free late days** during the semester. The final project is due based on the final grade submission date and cannot be turned in late. You do not need to tell us that you are applying your "late day" -- we'll remove the late penalty at the end of the semester from the assignment(s) that benefits you the most.

 Please plan your work on the assignments so that travel, interviews, athletics, touring, student clubs, extracurricular activities, religious holidays, etc. do not cause you to submit it late. None of the above reasons nor a heavy academic workload constitute an extraordinary circumstance.

 Many projects depend on earlier projects. *So even if you miss a deadline of a previous project, it is still important to finish it so you can build future projects on top of it.*

### Collaboration policy
Programming, like composition, is an individual creative process. Individuals must reach their own understanding of the problem and discover a path to its solution. During this time, you are encouraged to discuss your project with other students at the conceptual level. However, when the time comes to write the code that solves the problem, the program must be your own work.

Do not, under any circumstances, copy another person's program, comments, README description, or any part of the submitted assignment. This includes character-by-character transliteration of another works (whether inspected visually or copied digitally), but it also includes derivative works (i.e., by renaming variable names or subtly shifting around statements in order to try to hide that copying has occurred). You are also not allowed to use other people's code, comments, or results. This includes work done by other students this or past semesters, as well as any other code you find online.

You are also responsible for ensuring that the code you write for the assignments is not readable by others, which includes sharing with students in future years or posting publicly on websites like github.

You may possibly reuse functions from libraries, but you must check any packages/libraries that you plan to use with the TA’s. You should also mark on all the places where you reuse functions/libraries from other places. 

All programs will be subject to automated checking for similarity. Any cases of plagiarism will result in an F for the entire course. If you have any questions about policies about academic integrity, please talk to the professor.


## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)


## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)
