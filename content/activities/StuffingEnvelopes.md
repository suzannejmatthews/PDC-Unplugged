---
title: "StuffingEnvelopes"
date: 2020-01-07T14:10:46-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms"]
cs2013details: ["PD_4", "PD_5", "Algo_4", "Algo_5", "Algo_9"]
tcpp: ["TCPP_Programming", "TCPP_Algorithms"]
tcppdetails: ["C_Decomposition", "A_Dependencies"]
courses: ["K_12", "CS1", "CS2", "DSA", "Systems"]
senses: ["touch", "visual"]
medium: ["roleplaying", "envelopes"]

---

## Original Author/link

Originally described by Robert Chesebrough and Ivan Turner; the authors cite the 2nd chapter of James Reinders' book (see citations) as inspiration for this example.

No link to indepdendent description available. Please see Details section for more information.

---

## Details

Prior to the activity, students should be assigned to teams of four. The goal is to discuss different strategies for completing the stack of preparing letters for mailing. In doing the activity, students learn about domain (data) decomposition vs task decomposition. 

* **Domain (Data) Decomposition**: Each student "core" has a private stack of letters and performs the job of individually addresssing, stuffing and sealing each envelope prior to mailing it. 

* **Task Decomposition**: Each student was asked take on one or two particular tasks (e.g. stuffing and sealing). The team of "cores" then complete the tasks in a pipeline form; as one student finishes his or her set of tasks, the result was placed in a pile in front of of the other student to perform.

The students should recognize that due to dependencies between tasks, the level of parallelism is reduced.

---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Decomposition

4\. Parallelize an algorithm by applying task-based decomposition. [Usage]

5\. Parallelize an algorithm by applying data-parallel decomposition. [Usage]

### PD/Parallel Algorithms, Analysis and Programming 

4\. Identify independent tasks in a program that may be parallelized. [Usage]

5\. Characterize features of a workload that allow or prevent it from being naturally parallelized. [Familiarity]

9\. Give examples of problems where pipelining would be an effective means of parallelization. [Familiarity]

---

## TCPP Topics Coverage

### Programming Topics

* Comprehend Computation Decomposition Strategies: Understand different ways to assign computations to threads or processes.

### Algorithms Topics

* Apply Dependencies: Observe how dependencies constrain the execution order of subcomputations --- thereby lifting one from the limited domain of "embarrassing parallelism" to more complex computational structures



---

## Recommended Courses

* **K-12**: The authors shared the described unplugged activities with high school students. 

* **CS1/Systems**: TCPP recommends that the notion of dependencies can be introduced as early as CS1 and/or Systems

* **CS2/DSA**: TCPP recommends that decomposition strategies be introduced in CS2 or DSA.

---

## Accessibility

Students who are blind may have difficulty with this activity. 

---


## Assessment 

(Chesebrough2010) used unplugged activities as part of a larger three-day workshop for 16 high schoool students at Brookyn Tech in summer 2009. Chesebrough and Turner report that "the best part" of the camp was the role playing, and that the exercises helped drive concepts home. However, some of the more advanced students felt that the activities were "childish". However younger and/or less-experienced students enjoyed the role playing exercises.

---

## Citations

* R. A. Chesebrough and I. Turner. "Parallel computing: at the interface of high school and industry". In _Proceedings of the 41st ACM technical symposium on Computer science education (SIGCSE'10)_. pp. 280–284. Available: https://doi.org/10.1145/1734263.1734361

* J. Reinders. _Intel Threading Building Blocks: Outfitting C++ for Multi-Core Processor Parallelism_, O'Reilly Media Inc. 2007. 
