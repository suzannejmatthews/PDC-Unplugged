---
title: "PBJinParallel"
date: 2019-11-01T16:19:09-04:00
cs2013: ["PD_CommunicationAndCoordination"]
cs2013details: ["CAC_2"]
tcpp: ["TCPP_Programming", "TCPP_Algorithms"]
tcppdetails: ["C_Deadlocks", "K_DataRaces", "K_Synchronization"]
courses: ["CS0", "CS1", "CS2", "Systems", "OS"]
senses: ["movement", "touch"]
medium: ["roleplay", "food", "analogy"]

---

## Original Author/link

_Note: The "Make a Peanut Butter and Jelly Sandwich" serial exercise is an extremely old way to describe how a computer executes a set of instructions. The earliest known description is the "Great Peanut Butter Caper" by Lewandowski and Morehead in 1998. A variation was presented by Davis and Rebelsky in 2007. Unlike the original described exercises, this activity explores how to put together a Peanut Butter and Jelly sandwich in parallel_


[iPDC Modules](https://www.csc.tntech.edu/pdcincs/index.php/ipdc-modules/)

* Available in [Word](https://www.csc.tntech.edu/pdcincs/resources/modules/unplugged/pb&j_making/PBJ%20in%20Parallel.docx) and [PDF](https://www.csc.tntech.edu/pdcincs/resources/modules/unplugged/pb&j_making/PBJ%20in%20Parallel.pdf)

### Variation (Bogaerts2014)

Steve Bogaerts suggested using the example of making a PB&J sandwich as a way of explaining clock speed and explaining Moore's Law:

> "Suppose you tell someone to make one peanut butter and jelly sandwich every hour. That is easy to accomplish. Every minute? Perhaps possible, with a bit of practice. Every second? That would be impossible. A person can't be told to "speed up" beyond a certain point; some improvement in sandwich-making must be devised. Likewise, a processor cannot speed up with out some improvement in processor technology."



---

## CS2013 Knowledge Unit Coverage

### Communication and Coordination (Core Tier 1)

2\. **Core Tier 1**: Give an example of an ordering of accesses among concurrent activities (e.g., program with a data race) that is not sequentially consistent. [Familiarity]

---

## TCPP Topics Coverage

### Programming Topics

* Comprehend Deadlocks: Understand what a deadlock is, and methods for detecting and preventing them

*  Know Data Races: Know what a data race is, and how to use synchronization to prevent it.

### Algorithms Topics

*  Know Synchronization: Be aware of methods for controlling race conditions (1 hour)

---

## Recommended Courses

* **CS0/CS1/CS2**: The authors recommend that the concepts are appropriate for 
  all these levels. Might be challenging to do with large classrooms (and 
  perhaps too messy).

* **DSA/Systems**: In addition to CS2, TCPP recommends that DSA and Systems 
  courses may be appropriate places to cover synchronization, race conditions, 
  and deadlock. 

* **OS**: Concepts may also be appropriate in an OS course 
  where concurrency issues such as deadlock and race conditions are being 
  discussed.

---

## Accessibility

The "sandwich" concept can be extended to other cheap ingredients, in case
particular students have nut allergies or other food-related allergies. The 
most important part is to have a limited set of "ingredient" resources, and 
multiple people trying to access those resources.

There is a lot of movement involved in this exercise; we recommend that 
mobility-impaired students be encouraged to take on the role of a 
single student making sandwiches. 

---


## Assessment 

Activity Assessment Unknown.

(Bogaerts2014) used making a PB&J sandwich as an analogy for explaining clock speed and Moore's Law as part of a larger unit in parallelism in a CS1 course. He mentions that the total amount 
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

* J. Davis and S. A. Rebelsky. "Food-first computer science: starting the first course right with PB&J". _SIGCSE Bulletin_ 39(1) (March 2007), 372–376. DOI:https://doi.org/10.1145/1227504.1227440. 2007. 

* S. Bogaerts. "Limited Time and Experience: Parallelism in CS1". In _Proceedings of the 2014 IEEE 28th International Parallel & Distributed Processing Symposium Workshops  (IPDPSW'14)_, pp. 1071-1078. 2014.

* S. Bogaerts. "One step at a time: Parallelism in an introductory programming course". _Journal of Parallel and Distributed Computing_ Vol. 105, pp. 4-17. 2017.

* S. K. Ghafoor, M. Rogers, D. Brown, and A. Haynes, "ipdc modules (unplugged)" 
 last accessed Oct 16, 2019. [Online]. Available: https://www.csc.tntech.edu/pdcincs/index.php/ipdc-modules/

