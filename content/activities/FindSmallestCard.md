---
title: "FindSmallestCard"
date: 2019-12-09T14:34:15-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms"]
cs2013details: ["PD_2", "PD_4", "Algo_3", "Algo_4", "Algo_6"]
tcpp: ["TCPP_Algorithms", "TCPP_Programming"]
courses: ["CS1", CS2", "DSA"]
senses: ["touch", "visual"]
draft: true
---

## Original Author/link

Originally described by Gregory F. Bachelis, David A. James, Bruce R. Maxim and Quentin F. Stout (Bachelis1994)

No link to independent description publicly available. Please see details section for a synopsis.

### Similar Activites

[FindOldestPenny]({{<ref "activities/findoldestpenny">}}), [FindYoungestStudent]({{<ref "activities/findyoungeststudentinclass">}})

---

## Details

From (Bachelis1994):
The goal is to find the smallest card (e.g. lowest value card) in a collection of 16 cards. The notion of a "two-card comparator" is discussed as part of the process (e.g. input is two cards, outputs the smaller of the two cards). The processor therefore employs a series of "two-card comparators" to sort the set of cards.

### Serial case: 

* Students recognize that to find the smallest card in a collection of 16 cards, it should take 15 comparisons. 
* Ask the students: _how to make the process faster?_ 
* The answer is to to use several processors and a "divide and conquer" methodology.


### Parallel Case

**Two Students**:

* Each student is given 8 cards
* Each student finds the minimum of the 8; then a "global" comparison is made between the two students to determine the global minimum. 
* Ask the students: _how many time steps did this require?_ 
* Answer: To find the minimum of 8 cards, a total of 7 comparisons are required. Since each student performed their comparisons simultaneously and in parallel (and assuming that each comparison takes a time step), a total of 7 time steps are required. The final global comparison requires an additional time step. Therefore 8 total time steps are required.

**Four Students**:

* Each student is assigned a number (1..4) and is given a subset of 4 cards.
* Each student finds the minimum of their 4 cards. At the end, students 1 and 2 compare their minimums, with student 2 receiving the minimum. Likewise, students 3 and 4 compare their minimums, with student 4   
  receiving the minimum. Lastly, student 2 and 4 compare their minimum cards to determine the global minimum.
* Ask the students: _how many time steps did this require?_
* Answer: Each student initially takes 3 comparisons to find the minimum of 4 cards. Since the students performed their comparisons simultaneous and in parallel (and assuming that each comparison takes a time step), a total of three time steps are needed for this step. Next, the comparison between students 1 and 2 happen independently from the comparison of students 3 and 4, and therefore can occur in parallel. This 
additional comparison takes 1 time step. The final comparison between students 2 and 4 takes one additional time step. Therefore, the total number of time steps is 3 + 1 + 1 = 5. 

**Eight students**

* Each student is assigned a number (1..8) and given a subset of two cards.
* Each student finds the minimum of their two cards. Then: Students 1 and 2 compare their minimums with student 2 receiving the miniumum; Students 3 and 4 compare their minimums, with student 4 receiving the minimum; Students 5 and 6 compare their minimums, with student 6 receiving the minimum; Students 7 and 8 compare their minimums, wtih student 8 receiving the minimum. Next, students 2 and 4 compare their minimums, with student 4 receiving the result; students 6 and 8 compare their minimums, with stduent 8 receiving the result. Lastly, students 4 and 8 compare their final minimums, to output the global minimum.
* Ask the students: _how many time steps does this require?_
* Answer: Each student requires one time step to find the minimum of 2 cards. Since the students performed their comparisons simultaneous and in parallel (and assuming that each comparison takes a time step), a total of 1 time step is needed for this initial step. Next, note that the comparisons between students 1 and 2 happen independently from the comparison of students 3 and 4, and students 5 and 6, and students 7 and 8. These comparisons can therefore all happen in parallel, and take an additional time step. Next, observe that the comparison between students 2 and 4 happen independently from the comparison between students 6 and 8. These comparisons can therefore happen in parallel, and take an additional time step. The final comparison between sudents 4 and 8 requires one additional time step. Therefore, the total 
number of time steps is 1 + 1 + 1 + 1 = 4. 


The class then should asked to calculate the speedup of the parallel cases over the serial cases. 

---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Decomposition

**Core Tier 1:**

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]

**Core Tier 2:**

4\. Parallelize an algorithm by applying task-based decomposition. [Usage]

### PD/Parallel Algorithms, Analysis & Programming - Core Tier 2

3\. Define "speed-up" and explain the notion of an algorithm's scalability in this regard. [Familiarity]

4\. Identify independent tasks in a program that may be parallelized. [Usage]

6\. Implement a parallel divide-and-conquer (and/or graph algorithm) and empirically measure its performance relative to its sequential analog.


---

## TCPP Topics Coverage

### Programming Topics 

* Comprehend Performance Metrics (Speedup): Understand how to compute speedup, and what it means

### Algorithms Topics

* Comprehend Time: Recognize time as a fundamental computational resource that can be influenced by parallelism
* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling) 
* Apply Scheduling (Dependencies): Observe how dependencies constrain the execution order of subcomputations --- thereby lifting one from the limited domain of "embarrassing parallelism" to more complex 
  computational structures
* Comprehend Divide & conquer (parallel aspects): Observe, via tree-structured examples such as mergesort . . . how the same structure that enables divide and conquer (sequential) algorithms 
  exposes opportunities for parallel computation
* Know Selection: Observe algorithms for finding order statistics, notably min and max. Understand that selection can always be accomplished by sorting but that direct algorithms may be simpler.

---

## Recommended Courses

* **CS1**: TCPP recommends that the notion of dependencies be covered as early as CS1.
* **CS2/DSA**: TCPP recommends that concepts of speedup, divide-and-conquer and selection be covered in either CS2 or DSA.

---

## Accessibility

The visual aspect of this activity may make it less accessible for blind students. However, there are special decks of cards that have Braille printed on them. This will allow blind students to participate equally in this exercise. 

---


## Assessment 

Unknown. However, the related activities have asssessment.


---

## Citations

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.

* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel algorithms in undergraduate computer science courses (tutorial session)", in _Proceedings of the Twenty-first SIGCSE Technical Symposium 
  on Computer Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. Available: http://doi.acm.org/10.1145/323410.323415