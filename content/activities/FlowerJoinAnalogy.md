---
title: "FlowerJoinAnalogy"
date: 2020-01-08T16:01:45-05:00
tcpp: ["TCPP_Programming"]
tcppdetails: ["K_SharedMemoryLanguageExtensions"]
courses: ["CS1", "CS2", "DSA", "Systems", "ProgLang"]
senses: ["accessible"]
medium: ["analogy"]

---

## Original Author/link

 Originally described by Steve Bogaerts (Bogaerts2014).

 No link to independent description publicly available. See "Details" section for more details:

---

## Details

Bogaerts used this analogy to explain the notion of thread `join` operation. Suppose a parent and their child are out for a walk along a trail in their local park. The child decides to travel off the path to pick flowers.
While the parent can go on for some time without the child, eventually they will call out to the child to catch up: _"Come now, please join me up here"_. The parent will then wait for their child to join up with them, and then 
the two continue walking up the path together.

This is analogous to a main thread calling the `join()` operation on a child thread. Thread A blocks until B is finished; only then can A continue with their work.

 
---

## CS2013 Knowledge Unit Coverage

N/A

---

## TCPP Topics Coverage

### Programming Topics

* Know Shared Memory Language Extensions: Know about language extensions for parallel programming. Illustration from Cilk (spawn/join) and Java (Java threads)

---

## Recommended Courses

* **CS1**: Bogaerts used the analogy in a CS1 course 
* **CS2/DSA/Systems/ProgLang**: TCPP recommends that the notion of language extensions such as thread `join()` can be introduced in CS2, DSA, Systems and/or Programming Languages.
---

## Accessibility

Generally accessible.

---


## Assessment 

(Bogaerts2014) used flower analogy to explain the thread join operation as part of a larger unit in parallelism in a CS1 course. He mentions that the total amount 
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