---
title: "PlantingTrees"
date: 2020-01-08T11:16:31-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms", "PD_ParallelPerformance"]
cs2013details: ["PD_1", "PD_2", "PD_3", "PD_4", "PD_5", "Algo_4", "Algo_5", "Algo_9", "Perf_1"]
tcpp: ["TCPP_Programming", "TCPP_Algorithms"]
tcppdetails: ["C_Decomposition", "C_LoadBalancing", "C_Time", "A_Dependencies", "K_Dependencies"]
courses: ["CS1", "CS2", "DSA", "Systems", "ParProg"]
medium: ["analogy"]
---

## Original Author/link

Described by Yifat Ben-David Kolikant (Kolinkat2001). Two introduction questions presented by Steven Bogaerts as part of his "real-life analogies" (Bogaerts2014, Bogaerts2017).

No public description avaialable. See Details section for more information.

---

## Details

Start with some generals questions from Steven Bogaerts:

> "If I can shovel my driveway in 1 hour, how long would you expect it to take if someone equally capable were to help me?"

> "If one person can dig a hole with a shovel in 100 seconds, how long will it take for 10 people to dig that hole?"

The drive-way shoveling analogy is easy to split up and is relatively easy for students to recognize on how to do. The hole digging analogy is much harder to split up.  

To connect it better with the work of (Kolikant2001), we present a third question involving planting trees:

> "Suppose the goal is to plant 100 trees. Each tree requires than you dig a hole, place the tree in the hole, and refill the hole. Assume each of these steps takes 100 seconds. 
   How long does it take for one person to plant 1 tree? How about 100 trees? Suppose 10 people helped plant trees. How long will it take?"

* Students should be able to quickly identify that it takes one person 300 seconds to plant a single tree, and it would take that person 30,000 seconds (~8.33 hours) to plant 100 trees.
* The question of how to split up the work is interesting. If each person was responsible for planting 10 trees, then it would take roughly 3,000 seconds for all 10 people to finish 
  planting the 100 trees. This is a **data parallel** strategy. It is also potentially a good idea to ask what would happen if the first 9 people were assigned only 5 trees to plant, 
  while the 10th person got 55 trees to plant. Students should recognize that even though everyone is able to plant trees in parallel, the first 9 people will finish much sooner than 
  the 10th person, and everyone would have to wait until that person finishes for the task to be done. This scenario emphasizes the importance of **load-balancing**.


Now suppose instead of 10 people we have only 3, and each person followed the algorithm below to plant 100 trees in a straight line (Kolikant2001):

| Person 1  &nbsp; &nbsp; &nbsp; &nbsp;  &nbsp; &nbsp; &nbsp; &nbsp;  | Person 2 &nbsp; &nbsp; &nbsp;&nbsp;  &nbsp; &nbsp; &nbsp; &nbsp; | Person 3       |
| ----  |  ---- | ---- | 
| Do 100 times:  |  Do 100 times:  | Do 100 times:  |
| Dig hole       | Put tree in hole| Refill hole    | 
| Walk 2 meters| Walk 2 meters | Walk 2 meters|


<p>
While the actions on the hole must be performed in order, the algorithm does not explicitly state this. Students need to recognize the **dependencies** of execution between Persons 1 and 2, and between Persons 2 and 3. Students must explicitly state their assumptions (e.g. how long does it take each person to walk 2 meters? How long does it take for each gardener to complete their task?) and discuss scenarios in which the algorithm will work. 

* Some students may suggest that a central manager exists that directs the first person to dig all 100 holes, followed by the second person putting trees in all the holes, followed by the third person refilling all the holes. However, there is no parallelism in this solution, since each person does their work one after another. Another solution is that all three gardeners work on planting a single tree, before all going on to plant another. However, 
given the dependencies between the actions, it is again impossible for the three people to work in parallel in planting a single tree. 

* Some students may notice that is possible for all three people to be working on planting trees at once. This is a good place to discuss **pipelining** and how to calculate how long it will take for the three people to finish planting 100 trees.  

* It may be useful also to explain how in the most general case, each gardener has to be blocked on the gardener before them (wait-and-check) to do the task. This scenario does NOT include any assumption about how long it takes each gardener to complete their task, or how long it takes for the gardener to walk to the next hole. This is perhaps the most "realistic" scenario.


---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition

**Core Tier 1:**
1\. Explain why synchronization is necessary in a specific parallel program. [Usage]

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]

3\. Write a correct and scalable parallel algorithm. [Usage]

**Core Tier 2:**
4\. Parallelize an algorithm by applying task-based decomposition. [Usage]

5\. Parallelize an algorithm by applying data-parallel decomposition. [Usage]

### Parallel Algorithms, Analysis and Programming 

4\. Identify independent tasks in a program that may be parallelized. [Usage]

5\. Characterize features of a workload that allow or prevent it from being naturally parallelized. [Familiarity]

**Elective:**
9\. Give examples of problems where pipelining would be an effective means of parallelization. [Familiarity]


### Parallel Performance 

1\. Detect and correct a load imbalance. [Usage]

---

## TCPP Topics Coverage

### Programming Topics

* Comprehend Computation Decomposition Strategies: Understand different ways to assign computations to threads or processes

* Comprehend Load balancing: Understand the effects of load imbalances on performance, and ways to balance load across threads or processes

### Algorithms Topics

* Comprehend Time: Recognize time as a fundamental computational resource that can be influenced by parallelism (0.33 hours)

* Apply Dependencies: Observe how dependencies constrain the execution order of subcomputations --- thereby lifting one from the limited domain of "embarrassing parallelism" to more complex computational structures (0.5 hours)

* Know Dependencies: Understand the impacts of dependencies (0.5 hours)


---

## Recommended Courses

(Kolikant2001) presented the original exercise in an upper-level 
course on concurrency.

* **CS1**: Bogaerts presented his high-level questions in CS1. TCPP also recommends that dependencies can be introduced as early as CS1.
* **CS2/DSA**: TCPP recommends discussing decomposition strategies in CS2 or DSA.
* **Systems**: In addition to DSA, TCPP recommends discussing load balancing in systems courses. TCPP also recommends that dependencies be discussed in Systems courses.

---

## Accessibility

This assignment seems generally accessible. For students who are blind, the prompt needs to be made available in Braille (if given on paper). 

---


## Assessment 

(Kolikant2001) presented a component of the above as the second assignment in an upper-level 
course on concurrency. Despite the differences in the solutions, Kolikant found 
that she could classify all the responses into five main categories, including 
three centralized solutions, and two decentralized solutions. Found that many students
changed the problem to a simpler solution (e.g. each person received a third of the threes). 36.6% 
of the students identified that there were dependencies between the people planting trees, and 
assumed a constant rate of work for each. However, approximately half the students were able to 
identify that a "constant rate of work" is not realistic in real-life, including those that 
made the assumption. In post-interviews, some students mentioned that they used the constant rate assumption 
to make the algorithm "succeed". Students who took a decentralized view were in the minority; 
for example, one student in the post-interview said they were not comfortable using a pipelining approach, 
since it was unclear how long it would take each gardener to travel from one hole to another, and that it 
was theoretically possible for Person 2 to finish their work and travel to the next hole before Person 1 
finished their task of digging it. (Kolikant2001) argues that these findings support the notion 
that students have trouble orchestrating entities in decentralized systems.

(Bogaerts2014) used the analogies as part of a larger unit in parallelism. He mentions that the total amount 
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

* Y. B.-D. Kolikant, "Gardeners and cinema tickets: High school students' 
  preconceptions of concurrency", _Computer Science Education_, 11(3), 
  pp. 221–245, 2001. Available: https://doi.org/10.1076/csed.11.3.221.3831

* S. Bogaerts. "Limited Time and Experience: Parallelism in CS1". In _Proceedings of the 2014 IEEE 28th International Parallel & Distributed Processing Symposium Workshops  (IPDPSW'14)_, pp. 1071-1078. 2014.

* S. Bogaerts. "One step at a time: Parallelism in an introductory programming course". _Journal of Parallel and Distributed Computing_ Vol. 105, pp. 4-17. 2017.