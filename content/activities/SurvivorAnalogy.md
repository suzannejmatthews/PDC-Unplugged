---
title: "SurvivorAnalogy"
date: 2020-01-08T15:20:31-05:00
cs2013: ["PD_ParallelDecomposition", "PD_CommunicationAndCoordination"]
cs2013details: ["PD_1", "CAC_1"]
tcpp: ["TCPP_Algorithms"]
tcppdetails: ["A_Synchronization"]
senses: ["accessible"]
courses: ["CS1", "CS2", "DSA"]
medium: ["analogy"]

---

## Original Author/link
 
 Originally described by Steve Bogaerts (Bogaerts2014).

 No link to independent description publicly available. See "Details" section for more details:

---

## Details

This analogy is used to explain the mechanism of locks. While (Bogaerts2014) specifically references the book _The Lord of the Flies_, not everyone may be familiar with that book (and some who are may not want to be reminded of it). 
Instead, it may be useful to explain the following general scenario:

Imagine if a group of people are stranded on a deserted island. Occasionally, they must get together to make decisions. In order to prevent the meetings from getting chaotic, everyone agrees to a common rule that whoever holds a special conch shell is the only one who speaks. When the person speaking finishes, they put down the shell, enabling other people to compete for the shell. Whoever acquires it first is the person who speaks next. Other people must wait until the person speaking finishes, before they can attempt to get a turn.

In this analogy, the ship-wrecked people in the meeting represent threads or processes executing concurrently. The conch represents a lock, while the area where people talk represents a critical section. To ensure that communication is synchronized (and therefore intelligible), the conch enforces the rule that only one person talks at a time. Likewise, in order to ensure that processes or threads don't overwrite each other, locks ensure that only one thread or process enters a critical section at a time. 

---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition

1\. Explain why synchronization is necessary in a specific parallel program. 

### Communication and Coordination

1\. Use mutual exclusion to avoid a given race condition. [Usage]

---

## TCPP Topics Coverage

### Algorithms Topics

* Apply Synchronization: Be aware of methods for controlling race conditions (1 hour)

---

## Recommended Courses

* **CS1**: Bogaerts used the analogy in a CS1 course 
* **CS2/DSA**: TCPP recommends that synchronization concepts be covered in CS2 or DSA.

---

## Accessibility

Generally accessible. Some students may not be aware what a "conch shell" is, and it may be better to specify another object that all students are familiar with.

---


## Assessment 

(Bogaerts2014) used survivor analogy to explain locks as part of a larger unit in parallelism in a CS1 course. He mentions that the total amount 
of time spent on parallelism was larger in the section that used analogies and hands-on activities compared 
to the one that presented the topics in a traditional lecture-style format (4 hours vs 90 minutes). However, 
the section that used analogies and hands-on activities performed better than those who received the 
information in a traditional lecture-format. Bogaerts argues that it is much better to spend more time on 
fewer parallel concepts in a hands-on way in an introductory course, rather than covering a variety of 
parallel concepts in a non-hands-on way. The final conclusion drawn is that analogies and hands-on activities 
enabled students to learn better and stimulated greater interest in the subject than a course that 
delivered the material in a typical lecture-style fashion. (Bogaerts2017) extends the assessment of the 
original paper, but found that while student interest increased, the desire to learn more decreased. The authors
theorize that this is because most of the students in the course were non-majors who will not be pursuing 
computing in the future. 

---

## Citations

* S. Bogaerts. "Limited Time and Experience: Parallelism in CS1". In _Proceedings of the 2014 IEEE 28th International Parallel & Distributed Processing Symposium Workshops  (IPDPSW'14)_, pp. 1071-1078. 2014.

* S. Bogaerts. "One step at a time: Parallelism in an introductory programming course". _Journal of Parallel and Distributed Computing_ Vol. 105, pp. 4-17. 2017.
