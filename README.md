# CS 145, Spring 2021: Networking at Scale

## Overview

Modern networks have grown to extremely large scale (connecting millions of servers) and high speed (with Terabits per second) to meet the needs of a variety of cloud applications in business and society (e.g., social media, public health, and entertainment). In this course, we will study not only basic concepts in networking but also how these concepts get applied and extended for networking at scale. We will discuss the recent technology trends and design choices of performance, scalability, manageability, and cost faced by companies who own large-scale networks such as Amazon, Google, Microsoft, and Facebook. This course includes lectures and system programming projects.

- Instructor: Minlan Yu 
- Lecture time: MW 1:30pm-2:45pm
- Location: Check out Canvas zoom link
- Office hour: MW 2:45-3:30, class zoom link
- Discussion list: We are switching to [Ed](https://us.edstem.org/join/dBDbPe) this year
- Prerequisite: There are no official prerequisites. Recommended prep: system programming at the level of CS 61.


## Textbook
- This course covers both basic networking concepts and advanced cloud networking concepts.
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find [an online version](https://proquest-safaribooksonline-com.ezp-prod1.hul.harvard.edu/9780123850591) in Harvard library.
- There are no good textbook for cloud related concepts. You have to refer to my slides and class notes. We would love your contributions to the class notes too. Please feel free to add comments or suggest changes there.
   
## Coursework
- Class and biweekly section participation is mandatory.
- Extra credits given based on your contributions to in-class and piazza discussions.
- Programming projects: 75%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Midterm exam: 15%
- In-class and in-piazza participation 10%
  - including a networking news presentation.
- Please refer to the first lecture slides for details.


## Syllabus

| Weeks| Mon | Tue| Wed | Thu | Fri | Sat  | Sun |
|:-----------| :-----------|:-----------|:-----------|:-----------|:-----------|:-----------|:-----------|
| **Jan 25-Jan 31** | Course Overview | | L2/L3 (K&R 4.1-4.3, 6.1-6.3) | Project 1 (Topology) released | | | Project 0 due|
| **Feb 1-7**      | Data center topology (K&R 6.6)  | |  Discovery (K&R 6.4, 6.7)   |    |    Mininet tutorial | | 
| **Feb 8-14**    |     Routing basics (K&R 5.2, 5.3, 6.4)                  |     | Data Center routing  |   Project 2 (intradomain routing) released          |                      | | Project 1 due
| **Feb 15-21**    | No class <br> (President's Day) |      |    BGP Routing <br> data center BGP routing (K&R 5.4)  |                  | Routing tutorial|      |  |
| **Feb 22-Feb 28** | Networked Apps I (scalability, low latency)|      |     Networked Apps II (bandwidth, reliability)       |      Project 3 (ECMP)Released                 |  |    |     Project 2 Due 
| **Mar 1- Mar 7**      |   No class <br> (Wellness day)                                  |      |   Transport layer and TCP basics <br> *K&R 3.1-3.5*                     |   | P4 tutorial  |      |       
| **Mar 8-14**     |    Congestion control and fairness  <br> *K&R 3.6, 3.7.1*        |      |              Data Center TCP (K&R 3.7.2)                                                      |  Project 4 (reliable transport) released                  |                                             |      |       Project 3 due
| **Mar 15-21**    |     Traffic engineering basics, WCMP |      | CONGA |       |      Transport tutorial                                       |      |                           |
| **Mar 22-28**    |      Course Review for exams                                                                   |      |             Guest Lecture                                                 |      Project 5 (Flowlet) released              |                                           |      |   Project 4 due 
| **Mar 29-Apr 4** |network function  |      |        No class <br> (Wellness day)                                       |                    |                     Flowlet and CONGA tutorial                        |        |        |  
| **Apr 5-11**     |   Exam                          |      |       Load balancing                                   |   Project 6 (CONGA) released |                                        |   | project 5  due 
| **Apr 12-18**    |      Switches and P4                                                                                                                                                                 |      | Software defined networking(K&R4.4, 5.5)                                    |                                      |            Final project suggestions                                  |    |  | 
| **Apr 19-25**    |       WAN (wide-area networking)                                                                                                                                                                                            |      | Performance Isolation across tenants                                        |                          Project 7 released            |                                             | | project 6  due
| **Apr 26-May 2** | Security and Ethics  |      |        Course Summary                                                       |                          |             Final project proposal due                                 |     |      |
| **May 3-9**     |                                                                                                                                                                                                    |      |                                                               |                                        |                                             |      |                      |
| **May 10-16**    |                                                                                                                                                                                                    |      |                                                               |                                        | Final project due                           |      |                       |



## Project

### Objectives

This course project runs throughout the semester. Through this project you will reach two objectives

* Build a full stack data center network on your own laptop ranging from topology, routing, to applications.
* You will get hands-on experiences of the major concepts learnt in lectures and understand the tradeoffs of different design decisions

### [Infrastructure notes](infra.md) 

### Project Zero
You are supposed to finish [Project Zero](https://classroom.github.com/a/lhMcPJNy) before the class or in the first week of the class. Assignment 0 will not be graded. This is just a project for you to check if you are comfortable with the level of programming in this class and to set up infrastructure for future projects.

### Late policy
You should submit your work on an assignment (electronically) before its due time. All assignments will be due at `11:59pm ET` on the deadline date. 

If you submit your work late, we will award you a fraction of the score you would have earned on the assignments had it been turned in on time, according to this sliding scale:

* 90% for work submitted up to 24 hours late
* 80% for work submitted up to 2 days late
* 70% for work submitted up to 3 days late
* 60% for work submitted up to 5 days late
* 50% for work submitted after 5 days late

For example, if you should have earned 8/10 points but submitted 36 hours late, you will instead earn 6.4 points.

That said, you are allowed **TEN free late days** during the semester. The final project is due based on the final grade submission date and cannot be turned in late. You do not need to tell us that you are applying your *late day* -- we'll remove the late penalty at the end of the semester from the assignment(s) that benefits you the most.

Please plan your work on the assignments so that travel, interviews, athletics, touring, student clubs, extracurricular activities, religious holidays, etc. do not cause you to submit it late. None of the above reasons nor a heavy academic workload constitute an extraordinary circumstance.

Several projects depend on earlier projects. *So even if you miss a deadline of a previous project, it is still important to finish it so you can build future projects on top of it.* Here are the project dependencies:

```
  Project 0 (Setup) --> Project 1 (Topology) --> Project 3 (ECMP) --> Project 5 (Flowlet) --> Project 6 (CONGA)
  Project 2 (Intradomain routing)
  Project 4 (Reliable transport)
  Project 7 (Final project)
```

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
