---
title: "SieveOfErastothenes"
date: 2019-11-04T10:56:26-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelArchitecture", "PD_ParallelPerformance"]
cs2013details: ["PD_5", "Arch_1", Perf_1"]
tcpp: ["TCPP_Programming", "TCPP_Architecture", "TCPP_Algorithms", "TCPP_Pervasive"]
tcppdetails: ["C_Taxonomy", "A_DataParallel", "C_LoadBalancing", "C_DistributedMemory", "K_LoadBalancing", "A_SpecializedComputations"]
courses: ["CS2", "DSA", "Systems", "ProgLang"]
senses: ["movement", "visual"]
medium: ["paper", "boardwork"]
---

## Original Author/link
Originally described by Gregory F. Bachelis, David A. James, Bruce R. Maxim and Quentin F. Stout (Maxim1990, Bachelis1994).  Also described 
by Michelle Moore (Moore2000) and (Kitchen1992).

No web-link to independent description available. See papers (Bachelis1994, Moore2000) for 
additional details.

### Other activities by authors
(Bachelis1994): [ParallelAddition]({{<ref "activities/paralleladdition">}}), [FindSmallestCard]({{<ref "activities/findsmallestcard">}}), [OddEvenTranspositionSort]({{<ref "activities/oddeventranspositionsort">}})

(Moore2000): [CardSorting]({{<ref "activities/cardsorting">}}), [OddEvenTranspositionSort]({{<ref "activities/oddeventranspositionsort">}}), [MatrixAddition]({{<ref "activities/matrixaddition">}}) 

---

## Details

Suppose the goal is to find all the primes less than _n_ = 1,000. In the serial case, all the numbers from 2 .. 1000 would be written up on the board. The sieve of eratosthenes algorithm is 
then as follows:

1. Designated the first unmarked number as prime. 
2. Mark (cross out) all multiples of that number from the list.
3. Repeats steps 1 and 2, designating the next unmarked number as prime each time.

The question is next on how best to accomplish this algorithm in parallel.

### First attempt
Observe first that all even numbers are a multiple of 2. Therefore, it suffices to consider odd primes (and odd numbers) going forward. 
Next, determine the set of prime numbers that are less than `sqrt(n)`, and then cross out the multiples in the range of   `sqrt(n) .. n`.
In this case, `sqrt(1000)` is about 32, and the odd prime numbers between 3 .. 32 are 3, 5, 7, 11, 13, 17, 19, 23, 29, 31. Each student processor is then handed a subset of primes, and 
is asked to cross out the multiples of their primes. Thus, assuming there are 10 student processors, each student process is handed a separate prime, and crosses out the multiples of 
their prime in the matrix. 

An issue with this outlined approach is that larger primes necessarily have fewer multiples in the range. Therefore, student processors assigned the larger prime numbers have less work to perform than
students assigned smaller prime numbers. This highlights a load-balancing issue with this algorithm.

### Second attempt

The second version of the algorithm takes a data parallel approach. Each student is assigned a subset of _centuries_. Thus, if there are 10 student processors, each student is handed one century (shown below, 
from Bachelis1994):

```text
Century _00 to _99

_01  _03  _05  _07  _09 
_11  _13  _15  _17  _19 
_21  _23  _25  _27  _29 
_31  _33  _35  _37  _39 
_41  _43  _45  _47  _49 
_51  _53  _55  _57  _59 
_61  _63  _65  _67  _69 
_71  _73  _75  _77  _79 
_81  _83  _85  _87  _89 
_91  _93  _95  _97  _99 
```

So, student 0 is assigned the century 01 .. 99, while student 1 is assigned the century 101 .. 199, student 2 is assigned the century 201 .. 299 and so forth.  Note that student 0 will necessarily eliminate `1` from their matrix, since `1` is not prime. 

Students find the prime numbers in their century by following the algorithm below:

```text
for each number p in set of prime numbers
   divide the first number in the century by p and round up to the next highest integer. Call this number q.
   Now multiply this number by p (i.e., q = q * p)
   if q is even, add p to it. This is the first odd multiple of p in the century.
   cross out q (unless it is p).
   continue to add p to q, crossing out each multiple.
```

As an example, consider student 1 who is assigned the century 101 .. 199. 

* First, s/he divides 101 by 3, yielding 33.6, which rounds up to 34.
* 34 multiplied by 3 yields 102. Since 102 is even, 3 is added to yield 105. 
* Note that 105 is the first multiple of 3 in this century.
* The student then crosses out 105, 108, 111, etc. since they are all multiples of 3.
* The student then repeat the process with 101 and 5.

It should be pointed out to students that they are all running the same algorithm on different parts of data. This is an example of the SPMD (data paralllel) approach to parallel computing. It should also 
be pointed out that this approach is must better load balanced than the first attempt.

Students should now be able to clearly see how to extend the activity to find the set of odd primes less than 1 million. 

### Variation (Moore2000)
Moore describes an example exercise that she presents in a parallel processing 
lab to illustrate data parallelism. Originally, the exercise is meant to 
distinguish between task parallelism and data parallelism. The "First attempt" in (Bachelis1994)
is shown as an example of "control" (task) parallelism. The data parallel component of the 
exercise as shown in (Moore2000) is extrapolated below:

Prior to the start of the exercise, the instructor starts by writing as many 
integers as possible on the board (1-30 is recommended at the very least). To 
illustrate the data parallel model:

* students are selected to be processors, and the *n* values are divided amongst 
  the *s* students, so that each student has a partition of *n/s* of the data.

* Each student processor then marks the numbers in its portion of data that are divisible by 2, 3, 5, etc.

### Variation (Kitchen1992)

Kitchen et al. uses Sieve of Eratoshenes to distinguish between shared memory and distribted memory. For shared memory, the instructor initially 
writes all the numbers on a shared blackboard. Student threads each get assigned a component of the blackboard, perform the sieve on thier component and leaves. At the end, 
the blackboard will contain all the prime numbers.

The distributed memory description in (Kitchen1992) is ambiguous. Here is another way to show the distributed memory case. 
For distributed memory, the instructor (representing the boss process) assigns each student process a component of the matrix by sending them a pair of numbers (indicated the range).
This can be done by having the instructor throw piece of paper at the students (scatter), or walk to each individual desk to deliver message (send). Students can't start their work 
until they receive the message.  Once students receive the message, they enumerate the numbers in their assigned range on a piece of paper at their desks (local memory), and determine the primes in that range. They then "send" messages back to the instructor by either throwing a paper with the numbers into a waste-paper basket ("gather"), or handing their papers individually to the instructor ("send/receive").
The instructor then writes the received primes on the board.

---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Architecture (Core Tier 1)

1\. Explain the differences between shared and distributed memory. [Familiarity] 

### PD/Parallel Decomposition (Core Tier 2)

5\. Parallelize an algorithm by applying data-parallel decomposition.

### PD/Parallel Performance 

1. Detect and correct a load imbalance. [Usage]

---

## TCPP Topics Coverage

### Architecture Topics 

* Comprehend Parallel Taxonomy: Flynn's taxonomy, data vs. control parallelism, shared/distributed memory 

### TCPP Programming Topics

* Apply Data parallel: Be able to write a correct data parallel program for shared-memory machines and get speedup, should do an exercise.

* Comprehend Load balancing: Understand the effects of load imbalances on performance, and ways to balance load across threads or processes.

* Comprehend Distributed Memory: Know basic notions of messaging among processes, different ways of message passing, collective operations 

### TCPP Algorithm Topics

* Know Load Balancing: Understand that processors equitably sharing the computational/communication load among processors benefits the entire algorithm. That is, the most stretched processor determines the performance of the entire algorithm. Use a simple task graph (for example) with a small number of processors to illustrate the idea.

* Apply Deeper Algorithmic Experience: Experience through class instruction and assignment/project the design, analysis, and implementation aspects of at least one parallel or distributed algorithm of choice in detail. Master PDC algorithmic concepts through a detailed exploration, including recognizing how algorithm design reflects the structure of the computational problem(s) and the PDC model/environment.

---

## Recommended Courses

* Moore covers the concept in a parallel processing lab, though it is not 
  clear which course the lab was used in.

* **CS2/DSA/ProgLang** - TCPP recommends that data parallelism can be taught 
  in either CS2, DSA or programming languages.

* **Systems**: Architecture concepts can be taugh in Systems.

---

## Accessibility

Since this activity requires students to mark values on a board in front of 
the classroom, it may be challenging for mobility-impaired students or blind 
students.

---


## Assessment 

(Kitchen1992) mentions the shared vs. distributed memory aspect of this exercise was used effectively at various invited talks, in a classroom at RIT, and at least two workshops at Colgate University. However, formal evaluation is not provided. (Moore2000) discusses the 
impact of the parallel computing labs in her course. In general, students 
responded to the labs positively, and felt that labs increased their knowledge 
significantly.

---

## Citations

* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel algorithms in undergraduate computer science courses (tutorial session)", in _Proceedings of the Twenty-first SIGCSE Technical Symposium 
  on Computer Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. Available: http://doi.acm.org/10.1145/323410.323415

* A. T. Kitchen, N. C. Schaller, and P. T. Tymann, "Game playing as a technique for teaching parallel computing concepts", _SIGCSE Bulletin_, vol. 24, no. 3, pp. 35–38, Sept. 1992.
  Available: http://doi.acm.org/10.1145/142040.142064

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.

* M. Moore, "Introducing parallel processing concepts", *J. Comput. Sci. Coll.,* 
  vol. 15, no. 3, pp. 173–180, Mar. 2000. Available: http://dl.acm.org/citation.cfm?id=1852563.1852589

