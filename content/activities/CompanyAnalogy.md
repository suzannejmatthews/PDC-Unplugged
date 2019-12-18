---
title: "CompanyAnalogy"
date: 2019-11-01T17:02:44-04:00
cs2013: ["PD_ParallelArchitecture"]
cs2013details: ["Arch_2"]
tcpp: ["TCPP_Architecture", "TCPP_Programming"]
tcppdetails: ["K_MIMD", "K_TasksThreads", "C_Decomposition", "C_Static", "C_Dynamic"]
courses: ["oo_course", "systems"]
tags: ["analogy", "movement"]
draft: true
---

## Original Author/link

Originally described by Nasser Giacaman (Giacaman2012). 

No web-link to independent description available. See paper (Giacaman2012) for 
details.

---

## Details 

The company analogy is used to introduce multicore systems:

* The processor is a "company" with "desks" representing multiple cores.
* Students ("employees") are assigned/hired to sit at a desk to do work, representing threads (or processes).
* Work is written on "job cards" and represent tasks/runnables to be executed.   

To illustrate (under)utilization and resource contention/context switching:

* Optimally, one employee would be hired for every desk.
* If less employees are hired, then there are empty desks (under-utilization).
* If more employees are hired than there are desks, then some employees will have to wait until another employee gets up (resource contention) before sitting down (context switching).

To introduce static vs dynamic scheduling:

* **Static scheduling**: Each employee gets a subset of the job cards and sits at their desk until they are done.
* **Dynamic scheduling**: The cards start in a large pile in front of the room. When an employee is done processing their card, they request another card to process.


---

## CS2013 Knowledge Unit Coverage

### Parallel Architecture (Core Tier 2)

2\. Describe the SMP architecture and note its key features. [Familiarity]

---

## TCPP Topics Coverage

### Architecture Topics
* Know MIMD: Identify MIMD instances in practice (**multicore**, cluster, e.g.), and know the difference between execution of tasks and threads (0.1-0.5 hours)

### Programming Topics
* Know Tasks and threads: Understand what it means to create and assign work to threads/processes in a parallel program, and know of at least one way do that (e.g., OpenMP, Intel TBB, etc.) (0.5 hours)
* Comprehend Computation Decomposition Strategies: Understand different ways to assign computations to threads or processes
* Comprehend Static Scheduling and mapping: Understand how to map and schedule computations before runtime.
* Comprehend Dynamic Scheduling and mapping: Understand how to map and schedule computations at runtime.

### Algorithm Topics
* Comprehend Work: Observe the impact of computational work (e.g., the total number of tasks executed) on complexity measures such as power consumption (0.5 hours)

---

## Recommended Courses

* **OO** Giacaman used the analogies in a second year computer science course (beyond data structures) where students got their first taste of object-oriented programming.
* **Systems**: The analogies above would also be usedful in a Systems course.

---

## Accessibility

N/A

---


## Assessment 

Giacaman presented the analogies as a way of introducing programming concepts in 
a object oriented programming course. Of the 218 students in the course, 105 
completed survey. 93% of the students reported liking the way material was 
presented (47% strongly agree, 46% agree). Of the 105 respondents, 16 specifically 
mentioned the use of the analogies as being "most helpful" to their learning. 

---

## Citations

* N. Giacaman, "Teaching by example: Using analogies and live coding 
demonstrations to teach parallel computing concepts to undergraduate students" 
in *Proceedings of the 2012 IEEE 26th International Parallel and Distributed 
Processing Symposium Workshops & PhD Forum (IPDPSW'12)*, Washington, DC, USA: 
IEEE Computer Society, 2012, pp. 1295–1298. Available: http://dx.doi.org/10.1109/IPDPSW.2012.158
