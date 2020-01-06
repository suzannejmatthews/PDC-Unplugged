---
title: "StabalizingLeaderElection"
date: 2020-01-06T16:15:10-05:00
cs2013: ["PD_DistributedSystems", "PD_CloudComputing"]
cs2013details: ["DS_9", "CC_2"]
tcpp: ["TCPP_Algorithms", "TCPP_CrossCutting"]
tcppdetails: ["K_Asynchrony", K_FaultTolerance"]
courses: ["CS2", "Systems", "ParProg", "Graduate"]
senses: ["visual"]
medium: ["roleplaying"]
---

## Original Author/link

Originally described by Paulo A.G. Sivilotti and Scott Pike

[Paper](http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/sigcse07.pdf) available online:

---

## Details

See paper for full details. This activity demonstrates how an algorithm can recover from data corruption. The students in this activity represent processes in an undirected connected graph. Each process has a unique identifier. The goal is to identify the process with the highest identifier.  While the process identifiers themselves are not corruptible, the model assumes that transient faults may occur that can corrupt data values associated with the process. The corrupted data values can only be fixed by overwriting them with fresh values. 

* Prior to the activity, the instructor either manually assigns each student a unique process ID, or (as an alternative method) have each student's process ID be the last four digits of their telephone number.  Students sitting at desks that are adjacent to each other share edges. Furthermore, each student is given a flash-card which they use to record the highest process ID seen (called the candidate). 

* At the beginning of the activity, each student initializes their flash card with their own ID. 
* During the activity, each student periodically compares their values with their neighbors. If the neighbor has a higher value on their flash card, then the student updates their flash card with the higher value. If the student has the higher value, then the neighbor will update their flash card with the value on the student's card.
* The leader is elected when the majority of the cards have the same value.

### Illustrating the Intolerant Algorithm

* A student in the group surreptitiously changes their card to '9999' during the activity. 
* The value 9999 will then get propagated throughout the classroom. Eventually, it will get elected as "leader" (i.e., the highest value)
* The instructor should then ask the student with the process id '9999' to stand up. No one will stand up because it doesn't match anyone's process ID! This example illustrates how an error can propagate through the system.

### Stable Leader Election Algorithm

* Each student now has two flash cards; one that represents the candidate, and the other that represents distance.  
* As students compare cards with their neighbors, they take their neighbor's highest value as long as the distance does not exceed some small value _k_. If two neighbors have the same higher value, the students should copy the higher value from the student with the lower distance, and add 1 to it to get their distance. If the newly computed distance is greater than _k_, the student does not take the value.
* A student in the group surreptitiously changes their card to '9999'. However, since _k_ is small, the number of students that take on the corrupted value is minimal, and a non-corrupted process value will be elected leader.

---

## CS2013 Knowledge Unit Coverage


### PD/Distributed Systems

9\. Give examples of problems for which consensus algorithms such as leader election are required. [Usage]

### PD/Cloud Computing

2\. Explain strategies to synchronize a common view of shared data across a collection of devices.[Familiarity]	


---

## TCPP Topics Coverage

### Algorithms Topics

* Know Asynchrony: Understand asynchrony as exhibited on a distributed platform, its strengths (no need for synchs) and pitfalls (the danger of race conditions)

### Cross Cutting and Advanced Topics

* Know Fault tolerance: Large-scale parallel/distributed hardware/software systems are prone to components failing but system as a whole needs to work. (0.5 hours)

---

## Recommended Courses

The instructors used this activity in an upper-level undergraduate course on parallel programming. They also recommend the activity for graduate students.

* **CS2**: TCPP recommends that asynchronous communication can be introduced as early as CS2
* **Systems**: TCPP recommends that fault tolerance be introduced in a systems course.

---

## Accessibility

This activity may be difficult for blind students. 

---


## Assessment 

No assessment provided. 

---

## Citations


* P. A. G. Sivilotti and S. M. Pike, "The suitability of kinesthetic learning activities for teaching distributed algorithms", in _Proceedings of the
  38th SIGCSE Technical Symposium on Computer Science Education (SIGCSE'07)_, 2007, pp. 362–366.
  Available Online: http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/sigcse07.pdf. Also: http://doi.acm.org/10.1145/1227310.1227438
