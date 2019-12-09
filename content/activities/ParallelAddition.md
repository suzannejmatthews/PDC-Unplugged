---
title: "ParallelAddition"
date: 2019-12-09T15:43:45-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms"]
cs2013details: ["PD_2", "PD_4", "Algo_3", "Algo_4", "Algo_6"]
tcpp: ["TCPP_Architecture", "TCPP_Algorithms", "TCPP_Programming"]
courses: ["CS1", CS2", "DSA", "Systems"]
senses: ["touch", "visual"]
draft: true
---

## Original Author/link

Originally described by Gregory F. Bachelis, David A. James, Bruce R. Maxim and Quentin F. Stout (Bachelis1994)

No link to independent description publicly available. Please see details section for a synopsis.

### Other activities by (Bachelis1994)

[FindSmallestCard]({{<ref "activities/findsmallestcard">}})

---

## Details

From (Bachelis1994):
The goal is to add a series of 16 random numbers. Each student is given a piece of paper (representing local memory) that only they have access to. Addition can only be performed between two numbers at any given time, and it assumed that it takes the same amount of time to add any two numbers. Thus, one addition operation takes one time step. The processor therefore employs a series of addition operations to 
to add the collection of numbers. Each number is written down on a separate card. Note cards are also provided for "message passing".


### Serial case: 

* One student is given the set of 16 random numbers and is asked to add them up. 
* Student should recognize that to add 16 numbers, it takes a total of 15 addition operations. 
* Ask the students: _how to make the process faster?_ 
* The answer is to to use several processors and a "divide and conquer" methodology.


### Parallel Case

**Two Students**:

* Each student is given a subset of 8 numbers. 
* Each student adds their 8 numbers together on their own piece of paper. Student 1 then writes their total on a notecard and hands it to student 2. Student 2 then adds their total with the total they received  
  from student 1 to yield the final total. The class should note that this total is equal to total achieved during the serial run.
* Ask the students: _how many time steps did this require?_ 
* Answer: To add 8 numbers, a total of 7 addition operations are required. Since each student performed their additions simultaneously and in parallel, a total of 7 time steps are required. The final global 
  sum requires an additional time step. Therefore 8 total time steps are required, plus any overhead for the message by student 1 to student 2. 

**Four Students**:

* Each student is assigned a number (1..4) and is given a subset of 4 numbers to add up.
* Each student adds up thier 4 numbers (using their piece of paper). At the end, students 1 writes their total on an index card and hands it to student 2, who computes a new total using their total and the
  total received from student 1. Likewise, student 3 writes down their computed total won an index card and hands it student 4, who computes a new total by adding their total to the one received from student 3.
  Lastly, student 2 writes their new total on another index card and hands it to student 4, who computes the final total. The class should note that this amount is the same as the total value achieved before. 
* Ask the students: _how many time steps did this require?_
* Answer: Each student initially takes 3 addition operations to add 4 numbers. Since the students performed their comparisons simultaneous and in parallel, a total of three time steps are needed for this step. 
  Next, the communication of the sum from student 1 to 2 happen independently from the communication of the sum from student 3 to student 4, and students 2 and 4 compute their sums independently. Therefore, this step can also happen in parallel, and takes an additional time step (exclusive of communication costs). The final sum between students 2 and 4 requires on last time step. Therefore, the total number of time steps is 3 + 1 + 1 = 5, not including the overhead of message communication. Students should recognize that the number of "messages" sent by students have grown.

**Eight students**

* Each student is assigned a number (1..8) and given a subset of two cards.
* Each student adds their two numbers together. Then: Student 1 sends their total to Student 2, Student 3 sends their total to Student 4, Student 5 sents their total to Student 6, Student 7 sends their total to 
  Student 8. 
* During the next time step, Students 2, 4, 6, and 8 adds the number they receive with their total to produce new totals. Then, Student 2 sends their new total to Student 4, and Studet 6 sends their 
  total to Student 8. 
* During the next time step, Students 4 and 8 add the numbers they receive to their totals to produce new totals. Then, Student 4 sents their new total to Student 8.
* During teh last time step, Student 8 adds their total with the number they received from Student 4. This is the final total. Students should note that this total matches the totals computed in the 1, 2, and 4 
  processor scenarios. 
* Ask the students: _how many time steps does this require?_
* Answer: Each student requires one time add 2 numbers. Since the students performed their comparisons simultaneous and in parallel, a total of 1 time step is needed for this initial step. Next, the  addition 
  of student 1 and 2's totals happen independantly from the sums of students 3 and 4's totals, and student 5 and 6's totals, and students 7 and 8's totals. These additions all happen in parallel, and take an additional time step. Next, the summing of the totals for students 2 and 4 happen independently from the summing of the totals of students 6 and 8. These additions therefore happen in parallel, and take an
  additional time step. The final addition of the totals of students 4 and 8 requires one additional time step. Therefore, the total number of time steps is 1 + 1 + 1 + 1 = 4, excluding communication costs.


The class then should asked to calculate the speedup of the parallel cases over the serial cases. The students should see that speedup is not linear, and that the addition of more processors does incur heavier 
communication cost. To make the example more concrete, assign a cost to each communication component (0.5 time step). Then ask students to recompute time steps and speedup. This should help students clearly 
observe the cost of communication overhead.

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

### Architecture Topics

* Know Message passing (no shared memory) Latency: Know the concept, implications for scaling, impact on work/communication ratio to achieve speedup

### Programming Topics 

* Comprehend Performance Metrics (Speedup): Understand how to compute speedup, and what it means
* Know Performance Metrics (Amdahl's Law): Know that speedup is limited by the sequential portion of a parallel program, if problem size is kept fixed


### Algorithms Topics

* Comprehend Time: Recognize time as a fundamental computational resource that can be influenced by parallelism
* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling) 
* Apply Scheduling (Dependencies): Observe how dependencies constrain the execution order of subcomputations --- thereby lifting one from the limited domain of "embarrassing parallelism" to more complex 
  computational structures
* Comprehend Divide & conquer (parallel aspects): Observe, via tree-structured examples such as mergesort . . . how the same structure that enables divide and conquer (sequential) algorithms 
  exposes opportunities for parallel computation
* Know Selection: Observe algorithms for finding order statistics, notably min and max. Understand that selection can always be accomplished by sorting but that direct algorithms may be simpler.
* Comprehend/Apply Communication: Understand --- via hands-on experience --- that inter-processor communication is one of the most challenging aspects of PDC. 

---

## Recommended Courses

* **CS1**: TCPP recommends that the notion of dependencies be covered as early as CS1.
* **CS2/DSA**: TCPP recommends that concepts of speedup, divide-and-conquer and selection be covered in either CS2 or DSA.
* **Systems**: TCPP recommends that topics related to communicaton could be covered in Systems.

---

## Accessibility

The visual aspect of this activity may make it less accessible for blind students. However. students communicating a message to a blind partner can read their total aloud. The instructor can facillitate passing the total to the next student as necessary.

---


## Assessment 

Unknown. However, the related activities have asssessment.

---

## Citations

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.

* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel algorithms in undergraduate computer science courses (tutorial session)", in _Proceedings of the Twenty-first SIGCSE Technical Symposium 
  on Computer Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. Available: http://doi.acm.org/10.1145/323410.323415