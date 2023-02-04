# CS 145, Spring 2023: Networking at Scale

## ***Announcement***
- All future annoucements will happen at Ed. Please go to canvas-->Ed to join the forum there.
- **_[NEW]_ [2022/01/14] New x86 VM link is updated in [intrastructure setup](https://github.com/minlanyu/cs145-site/blob/spring2023/infra.md). This solves the problem that the previous VM cannot be run in VMware and also some libraries are fixed.**
- **_[NEW]_ [2022/01/14] [Project 0](https://classroom.github.com/a/i8-2KYy6) README (project description) is updated. Please run `./pull_update.sh` in your repository to update the project description.**
- **[2022/12/30] [Project 0](https://classroom.github.com/a/i8-2KYy6) and [intrastructure setup](https://github.com/minlanyu/cs145-site/blob/spring2023/infra.md) for spring 2023 are released! Please replace your VM with the latest version we provided if you download the 2021 version VM before 2022/12/30; otherwise, you might fail in running other CS-145 projects this year with the old VM.**
---

## Overview

This course studies computer network topics including Layer 2/Layer 3 topology, routing, transport protocols, traffic engineering, network functions, programmable switches, and software-defined networking. Modern networks have grown to large scale (connecting millions of servers) and high speed (Terabits per second) to meet the needs of cloud applications in business and society. Thus, in addition to learning the conventional concepts in networking, we will also discuss how to adapt these concepts to large-scale networks. These discussions will hopefully help deepen our understanding of networking technologies. This course includes lectures and system programming projects. 

- Instructor: Minlan Yu 
- Lecture time: T/TH 9:45-11am
- Lecture location: TBD
- Section time: Fridays 2-3pm every other week (available on demand for extension students). Please see the syllabus below on the actual dates for sections.
- Section location: SEC 3.302 + 3.303
- Minlan Office hour: Tue 11-12, SEC 4.415
- TF Office Hours (click [here](https://calendar.google.com/calendar/u/0?cid=Y180OTE0MzVlN2QyOGZhNDVhNzE1MzkyZWFhZjBjYWYxNzE1N2RmYWIwM2U0NmQxNWNkMzgxMTgxMjQ3YzQ3MmVjQGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20) to access the OH Google Calendar):
   - Mon 7-8:30 pm, online at [zoom](https://harvard.zoom.us/j/98554819683?pwd=eGxLWWcwSXphTUhCY1ZBSm5reVpkUT09)
   - Wed 8-9:30 pm, CS night in Winthrop Dining Hall
   - Fri 3-4:30 pm, hybrid: in-person in SEC 3.302 + 3.303, online at [zoom](https://harvard.zoom.us/j/93088044871?pwd=VlBGNXB0S3pXU29tV1d6d2dDT1QxQT09)
- TF: Vic Feng wfeng@g.harvard.edu, Alexander Pedersen pedersen@college.harvard.edu, Minghao Li minghaoli@g.harvard.edu 
- Prerequisite: There are no official prerequisites. Recommended prep: system programming at the level of CS 61.

## Textbook
- This course covers both basic networking concepts and advanced cloud networking concepts.
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach (7th edition), by Jim Kurose and Keith Ross. Earlier editions are fine. 
- An alternative book is Computer Networks: A Systems Approach (5th edition), by Larry Peterson and Bruce Davie. You can find an online version [here](https://book.systemsapproach.org/).
- For advanced topics of networking, please check out lecture notes and class slides.
   
## Coursework
### FAS version
- Class and biweekly section participation is mandatory.
- Programming projects: 70%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Homework: 5%
- Midterm exam: 15%
- In-class and Ed participation 10%
- Please refer to the first lecture slides for details.
- All assignments will be due at 11:59pm ET on the deadline date.

### Extension school version
- Classes and sections are can be attended by via live stream or on demand.
- Programming projects: 70%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Homework: 5%
- Midterm exam: 15%
- Ed participation 10%
- Note that the lecture slide version is for FAS class not extension school.
- All assignments will be due at 11:59pm ET on the deadline date.

## Syllabus

### Session 1: Network topology

### Week 1 (Jan 23-Jan 27)
* Tue class: Course Overview
   - Supplemental: [UMass Professor Explains the Internet in 5 Levels of Difficulty](https://www.youtube.com/watch?v=0EqKnvzo3no&t=1216s) by Jim Kurose
* Thu class: Link Layer
   - Textbook: K&R 6.1-6.4
* Thu: `Project 1 (Topology) released`
* Sun: `Project 0 checkin`

### Week 2 (Jan 30-Feb 3)
* Tue class: Data center topology, Spanning tree (K&R 6.6)
* Thu class: Ethernet routing, Network layer (K&R 4.1-4.3, 6.7)
* Fri section: Mininet tutorial (Alex)

### Session 2: Network routing

### Week 3 (Feb 6-Feb 10)
* Tue class: Network layer; Discovery protocols
* Thu class: Routing basics (K&R 5.2, 5.3, 6.4), Data Center routing
* Thu: `Project 2 (intradomain routing) released`
* Sun: `Project 1 due`

### Week 4 (Feb 13-Feb 17)
* Tue class: BGP Routing; data center BGP routing (K&R 5.4)
* Thu class: Networked Apps I (scalability, low latency)
* Fri section: Routing tutorial (Vic)

### Session 3: Network transport

### Week 5 (Feb 20-Feb 24)
* Tue class: Networked Apps II (bandwidth, reliability)
* Thu class:  Transport layer and TCP basics *K&R 3.1-3.5*
* Thu: `Project 3 (ECMP) Released`
* Sun: `Project 2 Due`

### Week 6 (Feb 27-Mar 3)
* Tue class: Congestion control and fairness *K&R 3.6, 3.7.1*
* Thu class: Data Center TCP (K&R 3.7.2)
* Thu: `Homework released`
* Fri section: P4 tutorial (Alex)

### Session 4: Traffic engineering

### Week 7 (Mar 6-Mar 10)
* Tue class: Traffic engineering basics, WCMP
* Thu class:  Course Review for exams
* Thu: `Project 4 (reliable transport) released`
* Fri section: Transport tutorial (Minghao)
* Sun: Project 3 Due

### Week 8 (Mar 13-Mar 17) Spring recess. No class
- Sun: `Homework due`

### Week 9 (Mar 20-Mar 24)
* Tue class:  Exam
   * Extension school students will take the exam on canvas on Mar 21-22. The exam will be available start at 9:45AM ET and will be available for 24 hours. You must finish the exam within 1 hour and 15 min of starting the exam.
* Thu class:  Guest lecture by Ying Zhang (Meta)
* Thur: `Project 5 (Flowlet) released`
* Sun: `Project 4 due`

### Week 10 (Mar 27-Mar 31)
* Tue class: Conga

### Session 5: Advanced network functions
* Thu class: Network functions
* Fri section: Flowlet and CONGA tutorial (Vic)

### Week 11 (Apr 3-Apr 7)
* Tue class: Load balancing
* Thu class: Switches and P4
* Thur: Project 6 (CONGA) released
* Sun: Project 5 due

### Session 5: Software-defined networking

### Week 12 (Apr 10-Apr 14)
* Tue class: Software defined networking (K&R4.4, 5.5)
   - Supplemental: [The Future of Networking, and the Past of Protocols](https://www.youtube.com/watch?v=YHeyuD89n1Y) by Scott Shenker
* Thur class: WAN (wide-area networking)
* Fri section: Final project suggestions (Minghao)

### Week 13 (Apr 17-Apr 21)
* Tue class: Security and Ethics
* Thur class: Performance Isolation across tenants
* Thur: `Project 7 released`
* Sun: `Project 6 due`

### Week 14 (Apr 24-Apr 28)
* Tue class: Course summary

### Week 15
- May 5 Friday: `Project 7 due`

## Project

### Objectives

This course project runs throughout the semester. Through this project you will reach two objectives

* Build a full stack data center network on your own laptop ranging from topology, routing, to applications.
* You will get hands-on experiences of the major concepts learnt in lectures and understand the tradeoffs of different design decisions

### [Infrastructure notes](infra.md) 

### Project Zero
You are required to finish [Project Zero](https://classroom.github.com/a/i8-2KYy6) before the class or in the first week of the class. Assignment 0 will not be graded. This is just a project for you to check if you are comfortable with the level of programming in this class and to set up infrastructure for future projects.

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


