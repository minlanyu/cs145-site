# CS 145, Spring 2024: Networking at Scale

## Overview

This course studies computer network topics including Layer 2/Layer 3 topology, routing, transport protocols, traffic engineering, network functions, programmable switches, and software-defined networking. Modern networks have grown to large scale (connecting millions of servers) and high speed (Terabits per second) to meet the needs of cloud applications in business and society. Thus, in addition to learning the conventional concepts in networking, we will also discuss how to adapt these concepts to large-scale networks. These discussions will hopefully help deepen our understanding of networking technologies. This course includes lectures and system programming projects. 

- Instructor: Minlan Yu 
- Lecture time: T/TH 9:45-11am
- Lecture location: TBD
- Section time: Fridays 2-3pm every other week (available on demand for extension students). Please see the syllabus below on the actual dates for sections.
- Section location: TBD
- Minlan Office hour: Tue 11-12, SEC 4.415
- TF:  
- TF Office Hours:
- Prerequisite: There are no official prerequisites. Recommended prep: system programming at the level of CS 61.

  ### Note: We are in the process of adjusting course projects (which significantly reduces the amount of P4 programming this year)

## Textbook
- This course covers both basic networking concepts and advanced cloud networking concepts.
- For basic networking concepts, you can refer to the textbook (K&R): Computer Networking: A Top-Down Approach, by Jim Kurose and Keith Ross. The latest edition is the 8th edition. Earlier editions are fine. The numbers in the syllabus are based on the 7th edition.
- An alternative book is Computer Networks: A Systems Approach, by Larry Peterson and Bruce Davie. You can find an online version [here](https://book.systemsapproach.org/).
- For advanced topics of networking, please check out lecture notes and class slides.
   
## Coursework
### FAS version
- Class and biweekly section participation is mandatory.
- Programming projects: 70%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Homework: 10%
- Midterm exam: 15%
- In-class and Ed participation 5%
- Please refer to the first lecture slides for details.
- All assignments will be due at 11:59pm ET on the deadline date.

### Extension school version
- Classes and sections are can be attended by via live stream or on demand.
- Programming projects: 70%
  - You will be building an example data center network on your laptop with seven projects, which include topology, routing, load balancing, failure recovery, measurement, and congestion control.
- Homework: 10%
- Midterm exam: 15%
- Ed participation 5%
- Note that the lecture slide version is for FAS class not extension school.
- All assignments will be due at 11:59pm ET on the deadline date.

## Syllabus

** Every week, there will be one or two homework questions which are released on Thursday and due the next Monday. It will just take a short time to finish but will serve as a way for you to get a recap of what we learnt last week to prepare for the new week. **

### Week 1 
* Jan 23 Tue class: Course Overview 
   - Supplemental: [UMass Professor Explains the Internet in 5 Levels of Difficulty](https://www.youtube.com/watch?v=0EqKnvzo3no&t=1216s) by Jim Kurose 
* Jan 25 Thu class: Network topology (K&R 6.6)
* Jan 25 Thu: `Project 1 (Topology) released`
* Jan 26 Fri section: Mininet tutorial
* Jan 28 Sun: `Project 0 checkin`

### Week 2 
* Jan 30 Tue class: Link layer: Ethernet (K&R 6.1-6.4)
* Feb 1 Thu class: Network layer: data plane: packet switching vs circuit switching (K&R 1.3)

### Week 3 
* Feb 6 Tue class: Network layer: Data plane: IP, ARP, DHCP (K&R 4.1-4.3, 6.4)
* Feb 8 Thu class:  
* Feb 8 Thu: `Project 2 (intradomain routing) released`
* Feb 9 Fri section: Routing tutorial
* Feb 11 Sun: `Project 1 due`

### Week 4 
* Feb 13 Tue class: Network layer: Control plane: Link state and distance vector (K&R 5.2, 5.3)
* Feb 15 Thu class: Network layer: data center routing (K&R 5.4)
* Feb 18 Sun: `Project 1 grading out`

### Week 5 
* Feb 20 Tue class: Network layer: Control plane: BGP; BGP in data centers
   - Supplemental: [The Future of Networking, and the Past of Protocols](https://www.youtube.com/watch?v=YHeyuD89n1Y) by Scott Shenker
* Feb 22 Thu class: Network layer: SDN in the control plane (K&R4.4, 5.5)
* Feb 22 Thu: `Project 3 (ECMP) Released`
* Feb 23 Fri section: P4 tutorial
* Feb 25 Sun: `Project 2 Due`

### Week 6 
* Feb 27 Tue class: Network layer: SDN in the data plane
* Feb 29 Thu class: Transport layer: TCP basics (K&R 3.1-3.5)
* Mar 3 Sun: `Project 2 grading out`

### Week 7 
* Mar 5 Tue class: Transport layer: TCP basics (cont.) 
* Mar 7 Thu class: Transport layer: Congestion control (K&R 3.6) 
* Mar 7 Thu: `Project 4 (reliable transport) released`
* Mar 8 Fri section: Transport tutorial 
* Mar 10 Sun: Project 3 Due

### Week 8  Spring recess. No class

### Week 9 
* Mar 19 Tue class:  Transport layer: TCP fairness (K&R 3.7.1)
* Mar 21 Thu class:  Transport layer: Data center TCP
* Mar 24 Sun: `Project 3 grading out`

### Week 10 
* Mar 26 Tue class: **Exam**
   * Extension school students will take the exam on canvas on Mar 21-22. The exam will be available start at 9:45AM ET and will be available for 24 hours. You must finish the exam within 1 hour and 15 min of starting the exam.
* Mar 28 Thu class: Guest lecture
* Mar 28 Thu: `Project 5 (bufferbloat) released` *Note project 5 is due in a week*
* Mar 29 Fri section: data center load balancing tutorial 
* Mar 31 Sun: `Project 4 due`

### Week 11 
* Apr 2 Tue class: Data center load balancing 
* Apr 4 Thu class: Wide area: Traffic engineering   
* Apr 4 Thu: `Project 6 (traffic balancing) released`
* Apr 7 Sun: `Project 5 due`
* Apr 7 Sun: `Project 4 grading out`

### Week 12 
* Apr 9 Tue class: Application: Internet application HTTP and DNS
* Apr 11 Thu class:  Application: Data center applications
* Apr 12 Fri section: Final project suggestions (Minghao)
* Apr 14 Sun: `Project 5 grading out` 

### Week 13 
* Apr 16 Tue class: Ethics
* Apr 18 Thu class: Application: Data center applications
* Apr 18 Thu: `Project 7 released`
* Apr 21 Sun: `Project 6 due`

### Week 14 
* Apr 23 Tue class: Course summary
* April 28 Sun: `Project 6 grading out`

### Week 15
- May 5 Fri: `Project 7 due` (Tentative)

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
  Project 0 (Setup) --> Project 1 (Topology) --> Project 3 (ECMP) --> Project 6 (Traffic balancing)
  Project 2 (Intradomain routing)
  Project 4 (Reliable transport)
  Project 5 (Bufferbloat)
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


![image](https://github.com/minlanyu/cs145-site/assets/1844406/d59d5a42-35c4-4504-99fd-e6b47cbe8a55)
