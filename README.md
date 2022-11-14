# CS 145, Spring 2023: Networking at Scale

## Overview

This course studies computer network topics including Layer 2/Layer 3 topology, routing, transport protocols, traffic engineering, network functions, programmable switches, and software-defined networking. Modern networks have grown to large scale (connecting millions of servers) and high speed (Terabits per second) to meet the needs of cloud applications in business and society. Thus, In addition to learning the conventional concepts in networking, we will also discuss how to adapt these concepts to large-scale networks. These discussions will hopefully help deepen our understanding of networking technologies. This course includes lectures and system programming projects. 

- Instructor: Minlan Yu 
- Lecture time: T/TH 9:45-11
- Location: TBD
- Office hour: Tue 11-12
- TF: TBD
- Prerequisite: There are no official prerequisites. Recommended prep: system programming at the level of CS 61.


## Textbook
- This course covers both basic networking concepts and advanced cloud networking concepts.
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find [an online version](https://proquest-safaribooksonline-com.ezp-prod1.hul.harvard.edu/9780123850591) in Harvard library.
- For advanced topics of networking, please check out lecture notes and class slides.
   
## Coursework
- Class and biweekly section participation is mandatory.
- Extra credits given based on your contributions to in-class and Ed forum discussions.
- Programming projects: 70%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Homework: 5%
- Midterm exam: 15%
- In-class and Ed participation 10%
  - including a networking news presentation.
- Please refer to the first lecture slides for details.


## Syllabus

### Session 1: Network topology

### Week 1 (Jan 23-Jan 27)
- Tue class: Course Overview
- Thu class: L2/L3 (K&R 4.1-4.3, 6.1-6.3)
```diff
- Thu: Project 1 (Topology) released
- Sun: Project 0 checkin 
```

### Week 2 (Jan 30-Feb 3)
- Tue class: Data center topology (K&R 6.6)
- Thu class: Discovery (K&R 6.4, 6.7)
- Fri section: Mininet tutorial 


### Session 2: Network routing

### Week 3 (Feb 6-Feb 10)
- Tue class: Routing basics (K&R 5.2, 5.3, 6.4)
- Thu class: Data Center routing
- Thu: Project 2 (intradomain routing) released
- Sun: Project 1 due

### Week 4 (Feb 13-Feb 17)
- Tue class: BGP Routing; data center BGP routing (K&R 5.4)
- Thu class: Networked Apps I (scalability, low latency)
- Fri section: Routing tutorial

### Session 3: Network transport

### Week 5 (Feb 20-Feb 24)
- Tue class: Networked Apps II (bandwidth, reliability)
- Thu class:  Transport layer and TCP basics *K&R 3.1-3.5*
- Thu: Project 3 (ECMP) Released
- Sun: Project 2 Due

### Week 6 (Feb 27-Mar 3)
- Tue class: Congestion control and fairness *K&R 3.6, 3.7.1*
- Thu class: Data Center TCP (K&R 3.7.2)
- Thu: Homework released
- Fri section: P4 tutorial

### Session 4: Traffic engineering

### Week 7 (Mar 6-Mar 10)
- Tue class: Traffic engineering basics, WCMP
- Thu class:  Course Review for exams
- Thu: Project 4 (reliable transport) released
- Sun: Project 3 Due

### Week 8 (Mar 13-Mar 17) Spring recess. No class
- Sun: Homework due

### Week 9 (Mar 20-Mar 24)
- Tue class:  Exam
- Thu class:  Guest lecture by Ying Zhang (Meta)
- Thur: Project 5 (Flowlet) released
- Fri: Transport tutorial
- Sun: Project 4 due

### Session 5: Network devices

### Week 10 (Mar 27-Mar 31)
- Tue class: Conga
- Thu class: Network functions

### Week 11 (Apr 3-Apr 7)
- Tue class: Load balancing
- Thu class: Switches and P4
- Fri: Flowlet and CONGA tutorial
- Thur: Project 6 (CONGA) released
- Sun: Project 5 due

### Session 5: Software-defined networking

### Week 12 (Apr 10-Apr 14)
- Tue class: Software defined networking(K&R4.4, 5.5)
- Thur class: WAN (wide-area networking)

### Week 13 (Apr 17-Apr 21)
- Tue class: Performance Isolation across tenants
- Thur class: Security and Ethics
- Thur: Project 7 released
- Fri: Final project suggestions
- Sun: Project 6 due

### Week 14 (Apr 24-Apr 28)
- Tue class: Course summary

### final weeks
- Project 7 due

## Project

### Objectives

This course project runs throughout the semester. Through this project you will reach two objectives

* Build a full stack data center network on your own laptop ranging from topology, routing, to applications.
* You will get hands-on experiences of the major concepts learnt in lectures and understand the tradeoffs of different design decisions

### [Infrastructure notes](infra.md) 

### Project Zero
You are supposed to finish [Project Zero](https://classroom.github.com/a/oWARRAGX) before the class or in the first week of the class. Assignment 0 will not be graded. This is just a project for you to check if you are comfortable with the level of programming in this class and to set up infrastructure for future projects.

### Late policy
You should submit your work on an assignment (electronically) before its due time. All assignments will be due at `11:59pm ET` on the deadline date. 

If you submit your work late, we will award you a fraction of the score you would have earned on the assignments had it been turned in on time, according to this sliding scale:

* 90% for work submitted up to 24 hours late
* 80% for work submitted up to 2 days late
* 70% for work submitted up to 3 days late
* 60% for work submitted up to 5 days late
* 50% for work submitted after 5 days late

For example, if you should have earned 8/10 points but submitted 36 hours late, you will instead earn 6.4 points.

That said, you are allowed **SIX free late days** during the semester. The final project is due based on the final grade submission date and cannot be turned in late. You do not need to tell us that you are applying your *late day* -- we'll remove the late penalty at the end of the semester from the assignment(s) that benefits you the most.

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

Do not, under any circumstances, copy another person's program, comments, README/Report description, or any part of the submitted assignment. This includes character-by-character transliteration of another works (whether inspected visually or copied digitally), but it also includes derivative works (i.e., by renaming variable names or subtly shifting around statements in order to try to hide that copying has occurred). You are also not allowed to use other people's code, comments, or results. This includes work done by other students this or past semesters, as well as any other code you find online.

You are also responsible for ensuring that the code you write for the assignments is not readable by others, which includes sharing with students in future years or posting publicly on websites like github.

You may possibly reuse functions from libraries, but you must check any packages/libraries that you plan to use with the TF’s. You should also mark on all the places where you reuse functions/libraries from other places. 

All programs will be subject to automated checking for similarity. Any cases of plagiarism will result in an F for the entire course. If you have any questions about policies about academic integrity, please talk to the professor.


## Diversity and Inclusion
I would like to create a learning environment in our class that supports a diversity of thoughts, perspectives and experiences, and honors your identities (including race, gender, class, sexuality, socioeconomic status, religion, ability, etc.). I (like many people) am still in the process of learning about diverse perspectives and identities. If something was said in class (by anyone) that made you feel uncomfortable, please talk to me about it. If you feel like your performance in the class is being impacted by your experiences outside of class, please don’t hesitate to come and talk with me. As a participant in course discussions, you should also strive to honor the diversity of your classmates. (Statement extracted from one by Dr. Monica Linden at Brown University.)


## Accommodations for Disabilities
If you have a health condition that affects your learning or classroom experience, please let me know as soon as possible. I will, of course, provide all the accommodations listed in your AEO letter (if you have one), but sometimes we can do even better if a student helps me understand what really matters to them. (Statement adapted from one by Prof. Krzysztof Gajos.)

## Policies for Extension School Students

### Academic Integrity Policy
You are responsible for understanding Harvard Extension School policies on [Academic Integrity](https://extension.harvard.edu/for-students/student-policies-conduct/academic-integrity/) and how to use sources responsibly. Violations of academic integrity are taken very seriously. Visit [Using Sources Effectively and Responsibly](https://extension.harvard.edu/for-students/support-and-services/using-sources-effectively-and-responsibly/) and the [Harvard Guide to Using Sources](https://usingsources.fas.harvard.edu/) to review important information on academic citation rules. 

### Accessibility Services Policy
The Division of Continuing Education (DCE) is committed to providing an accessible academic community. The [Accessibility Services Office (ASO)](https://extension.harvard.edu/for-students/support-and-services/accessibility-services/) is responsible for providing accommodations to students with disabilities. Students must request accommodations or adjustments through the ASO. Instructors cannot grant accommodation requests without prior ASO approval. It is imperative to be in touch with the ASO as soon as possible to avoid delays in the provision of accommodation. 
DCE takes student privacy seriously. Any medical documentation should be provided directly to the ASO if a substantial accommodation is required. If you miss class due to a short-term illness, notify your instructor and/or TA but do not include a doctor's note. Course staff will not request, accept, or review doctor's notes or other medical documentation. For more information, email accessibility@extension.harvard.edu. 

### Publishing or Distributing Course Materials Policy
Students may not post, publish, sell, or otherwise publicly distribute course materials without the written permission of the course instructor. Such materials include, but are not limited to, the following: lecture notes, lecture slides, video, or audio recordings, assignments, problem sets, examinations, other students’ work, and answer keys. Students who sell, post, publish, or distribute course materials without written permission, whether for the purposes of soliciting answers or otherwise, may be subject to disciplinary action, up to and including requirement to withdraw. Further, students may not make video or audio recordings of class sessions for their own use without written permission of the instructor. 


