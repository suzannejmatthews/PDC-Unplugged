---
title: "MatrixAddition"
date: 2019-11-04T09:38:59-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms", "PD_ParallelArchitecture", "PD_ParallelPerformance"]
tcpp: ["TCPP_Architecture", "TCPP_Programming", "TCPP_Algorithms"]
courses: ["CS2", "DSA", "Systems"]
senses: ["movement", "visual"]
draft: true
---

## Original Author/link

Originally Described by Michelle Moore (Moore2000)

No web-link to independent description available. See paper (Moore2000) for 
additional details.

---

## Details

Moore describes how to use Matrix Addition to describe the differences 
between shared memory vs distributed memory systems. Prior to the start 
of the exercise, the instructor writes *N* x *M* matrices A and B on the board, 
along with an empty matrix C of the same dimensions. 

**Shared Memory**:

* One student is designated as the master. He or she picks a team of students to 
  help and splits up the *N*<sup>2</sup> cells between them.
* Each student is responsible to add up their corresponding cells in A and B and 
  write the result in C.  

Here, each student represents a thread, with the board representing shared 
memory. If there are too many students up on the board, many will start 
bumping into each other, signifying resource contention. Assigning fewer 
students (say one student per row) will likely lead to less contention.

**Distributed Memory**:

* One student is designated as the master process and stands at the front of 
  the classroom next to the board. He or she picks a subset of students at 
  their desks to help; these student helpers remain at their desk.
* The student representing the master process splits up the matrix and hands 
  each student helper the set of calculation to perform, including giving 
  themselves some work. 
* Once each student finishes their work, they hand their computations to the 
  master. The master then writes the result in the corresponding cell in 
  matrix C on the board.  

Here, each student represents a process (sitting at a separate node), and the 
master-worker pattern is illustrated. The board is the memory of the master 
node. 

Once students are used to the exercise, issues like task granularity and 
load balancing can be discussed, along with communication overhead:

* If too many students are picked, too many students get up and move around,  
  and the master has to work extra to send and receive all the extra messages.
* If too few students helpers are picked, it may take a long time to compute the matrix.
* If some students have more work than the others, then the time to complete the 
  computation of matrix C is dependent on the slowest student. 

---

## Variations

The following variations are suggested:

**Matrix Multiplication**: The above activity can easily be used to illustrate 
matrix multiplication by having the master assign each row to a separate 
student helper. To ensure that students can complete the multiplication in a 
reasonable about of time, reduce the range of values in matrices A and B (say 
to 1..5). 

**Heterogeneous Distributed Architectures**: For heterogeneous architectures, 
push desks together to form "multicore" nodes. Each group of desks has a large 
piece of paper on it, signfying shared memory. 

When the master sends a message, it is sent to the "team leader" at the desk, 
who then splits the work to his or her team at adjacent desks 
(representing individual threads). Each person in the team fills out the cells 
in the matrix assigned to them. Once the paper is completely filled in, the 
team leader takes the paper, and gives it to the master at the front of the 
class, who fills in the associated cells in matrix C. 

To illustrate a multicore master node, simply have the student playing the master node select a set of 
"mini-masters" to stand in front with them, and do an initial split of 
the matrix (i.e. one row to a "master"). Then each master will send a subset 
of their assigned cells to student team leaders at desks; the activity then 
continues as normal.

---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition (Core Tier 1)

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]

### Parallel Algorithms (Core Tier 2, Elective)

4\. **Core Tier 2**: Identify independent tasks in a program that may be parallelized. [Usage]

10\. **Elective**: Implement a parallel matrix algorithm. [Usage]

### Parallel Architecture (Core Tier 1)

1\. Explain the differences between shared and distributed memory. [Familiarity]

### Parallel Performance (Elective)

3\. Describe how data distribution/layout can affect an algorithm's communication costs. [Familiarity] 

---

## TCPP Topics Coverage

### Architecture Topics

* MIMD instances in practice (multicore, cluster, e.g.), and know the difference between execution of tasks and threads.
* Comprehend Multicore: Describe how cores share resources (cache, memory) and resolve conflicts.
* Comprehend Shared vs. distributed memory (SMP Buses): Systems Single resource, limited bandwidth and latency, snooping, scalability issues.


### Programming Topics

* Comprehend Distributed Memory: Know basic notions of messaging among processes, different ways of message passing, collective operations.
* Know Hybrid: Know the notion of programming over multiple classes of machines simultaneously (CPU, GPU, etc.).

### Algorithms Topics
* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling)
* Understand --- via hands-on experience --- that inter-processor communication is one of the most challenging aspects of PDC.
* Apply Specialized computations: Master one or two from among computations such as: matrix product, transposition, convolution, and linear systems; recognize how algorithm design reflects the structure of the computational problems.

---

## Recommended Courses

* Moore covers the concept in a parallel processing lab, though it is not 
  clear which course the lab was used in.

* **CS2/DSA/Systems** While TCPP recommends that concepts such as matrix 
  multiplicaton can be introduced as early as CS2, they recommend that several 
  of the programming and algorithmic topics be covered in DSA. Architecture 
  topics (and the notion of hybrid programming) are suggested for a systems course.


---

## Accessibility

This exercise requires movement. and may be difficult for students who are 
mobility impaired. However, these students can be included in the distributed 
portion of the exercise, as they can remain at their desk. Blind students 
will need Braille cards associated with the numbers that they need add/multiply 
handed to them. Teammates at the desk can hand them the appropriate cards.

---

## Assessment 

Assessment of this particular exercise is unknown; (Moore2000) discusses the 
impact of the parallel computing labs in her course. In general, students 
responded to the labs positively, and felt that labs increased their knowledge 
significantly.

---

## Citations

* M. Moore, "Introducing parallel processing concepts", *J. Comput. Sci. Coll.,* 
  vol. 15, no. 3, pp. 173–180, Mar. 2000. Available: http://dl.acm.org/citation.cfm?id=1852563.1852589
