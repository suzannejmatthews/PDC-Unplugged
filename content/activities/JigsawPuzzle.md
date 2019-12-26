---
title: "JigsawPuzzle"
date: 2019-11-04T13:12:43-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms", "PD_ParallelArchitecture", "PD_ParallelPerformance"]
cs2013details: ["PD_1", "PD_2", "Algo_3", "Algo_4", "Arch_1", "Arch_8", "Perf_1", "Perf_2", "Perf_3", "Perf_5"]
tcpp: ["TCPP_Architecture", "TCPP_Programming", "TCPP_Algorithms"]
tcppdetails: ["K_MIMD", "C_Multicore", "K_Latency", "C_LoadBalancing", "C_Static", "C_Dynamic", "K_Data", "C_Speedup", "C_Scaling", "CA_Communication"]
courses: ["K-12"]
senses: ["analogy", "visual", "touch"]
draft: true
---

## Original Author/link

Oklahoma Supercomputing Center for Educaton and Research
([OSCER](http://www.oscer.ou.edu/education.php))


"Supercomputing in Plain English" - Overview, Slides 45-52.

* Available in: [PPT](http://www.oscer.ou.edu/Workshops/Overview/sipe_overview_20180123.pptx) and [PDF](http://www.oscer.ou.edu/Workshops/Overview/sipe_overview_20180123.pdf)
* Also described in (Neeman2006)

---

## Variations

It is theoretically possible to "act out" the analogy by using an actual 
puzzle. However, the puzzle needs to be small enough to enable students to 
complete the puzzle in a reasonable amount of time. This variation is 
described in (Neeman2006):

**Shared Memory:**

* Suppose *A* is working on a jigsaw puzzle (give them a puzzle), and it takes 
them an hour to complete the puzzle.

* Now suppose *B* sits down at the table across from *A* (another volunteer 
sits at table). 

* If *A* does the half part of the puzzle, and *B* does the lower half, how 
  long will it take them to complete the puzzle?

* If *A* and *B* both try to grab a piece out of the pile at the same time, will 
  that slow them down? What if they try to grab the same piece?

* Can *A* and *B* really work completely independently, or will they have to 
  work on some parts together?

* Will these issues slow them down? If so, how much? 

* What if new people *C* and *D* sit down at the table to help (have two more 
  volunteers join them)? How long will it take four people? Will there be 
  more, less or about the same level of resource contention? What if we 
  increased the number to helpers to 8?

The above questions lead to a discussion about overhead issues such as 
contention for shared resources. While in a no-overhead situation it would 
take 30 minutes for two people to complete the puzzle, communication overhead 
will cause the puzzle to take more than 30 minutes to complete. Adding more 
people increases the communication overhead, and the discussing turns to 
the notion of diminishing returns.

**Distributed Memory:**

Everyone except for *A* and *B* goes back and returns to their seats. Pull 
out a different puzzle, this time where the pieces for *A* and the pieces of 
*B* are in different baggies. Ask *B* to go to another table across the room.

* Looking at this new arrangement, will there be more, less or the same amount 
  of contention for shared resources?

* What happens when *A* and *B* need to combine their puzzles together (i.e. 
  what about communication)? Will doing this kind of communication take more 
  or less time than when *A* and *B* were sitting together at the same table?

* Suppose *C* and *D* are given additional piles of puzzle pieces, so that 
  each person has 1/4th of the work. What will happen to communication cost?

* What if one student has twice as many pieces as another student? How does 
  that impact when the puzzle finishes? What if the two students are working 
  at the same rate? What if the first student is faster than the second?

The above questions enable students to see that while there is less resource 
contention, the communication cost gets more expensive. As more students 
are added, there is additional communication cost. The discussion then 
transitions to load balancing. Students learn that if processor speeds are 
equal, then work should be balanced amongst them. However, if one processor 
is much faster than the other, then that processor should get additional work
(Neeman2006).


---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition (Core Tier 1)

1\. Explain why synchronization is necessary in a specific parallel program. [Usage]

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]


### Parallel Algorithms, Analysis and Programming (Core Tier 2)

3\. Define "speed-up" and explain the notion of an algorithm's scalability in this regard. [Familiarity]

4\. Identify independent tasks in a program that may be parallelized. [Usage]

### Parallel Architecture (Core Tier 1, Elective)

1\.  **Core Tier 1**: Explain the differences between shared and distributed memory. [Familiarity]

8\. **Elective**:  Describe the key performance challenges in different memory and distributed system topologies. [Familiarity]

### Parallel Performance (Elective)

1\. Detect and correct a load imbalance. [Usage]

2\. Calculate the implications of Amdahl's law for a particular parallel algorithm. [Usage]

3\. Describe how data distribution/layout can affect an algorithm's communication costs. [Familiarity]

5\. Explain the impact of scheduling on parallel performance. [Familiarity]

---

## TCPP Topics Coverage

### Architecture Topics

* Know MIMD:Identify MIMD instances in practice (multicore, cluster, e.g.), and know the difference between execution of tasks and threads.

* Comprehend Multicore: Describe how cores share resources (cache, memory) and resolve conflicts.

* Know Message passing Latency: Know the concept, implications for scaling, impact on work/communication ratio to achieve speedup.

### Programming Topics 

* Comprehend Load balancing: Understand the effects of load imbalances on performance, and ways to balance load across threads or processes.
* Comprehend Static Scheduling and mapping: Understand how to map and schedule computations before runtime	DSA/Systems	
* Comprehend Dynamic Scheduling and mapping: Understand how to map and schedule computations at runtime	DSA/Systems	
* Know Data: Understand impact of data distribution, layout and locality on performance; know false sharing and its impact on performance (e.g., in a cyclic mapping in a parallel loop); notion that transfer of data has fixed cost plus bit rate (irrespective of transfer from memory or inter-processor) (1 hour)
* Comprehend Speedup: Understand how to compute speedup, and what it means.

### Algorithms Topics 

* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling).
* Comprehend/Apply Communication: Understand --- via hands-on experience --- that inter-processor communication is one of the most challenging aspects of PDC.


---

## Recommended Courses

* Authors present the analogy to attendees of their "Supercomputing in Plain English" workshop series. According to (Neeman2008), the concepts have been presented to students as young as elementary school to adult attendees. 
* **K-12**: The analogy is appropriate for K-12. Actually *doing* a puzzle in class may be most appealing to some classrooms. However, the *size* of the puzzle matters a lot here. If a puzzle with too many pieces is chosen, 
   the activity can take a really long time to complete. Be careful.
* **DSA/Systems** TCPP recommends that DSA and Systems courses are appropriate 
  places to introduce concepts such as static vs dynamic scheduling and 
  load balancing. In addition, architecture topics may be most appropriate in a 
  Systems course.


---

## Accessibility

The analogy and exercise are very visual; this exercise may not be appropriate 
for blind students.

---


## Assessment 

Unknown. (Neeman2006) describes the different analogies. There is no assessment 
provided in (Neeman2006) or (Neeman2008).

---

## Citations
* OSCER. "Overview: What the Heck is Supercomputing?". *Supercomputing in 
  Plain English: A High Performance Computing Workshop Series*. Online, 
  last accessed 5 November 2019. http://www.oscer.ou.edu/Workshops/Overview/sipe_overview_20180123.pdf
 
* H. Neeman, L. Lee, J. Mullen, and G. Newman, "Analogies for teaching parallel 
computing to inexperienced programmers", in *Working Group Reports on ITiCSE 
on Innovation and Technology in Computer Science Education*, ser. ITiCSE-WGR'06. 
New York, NY, USA: ACM, 2006, pp. 64–67. Available: http://doi.acm.org/10.1145/1189215.1189172

* H. Neeman, H. Severini, and D. Wu, "Supercomputing in plain english: Teaching
cyberinfrastructure to computing novices" *SIGCSE Bull.*, vol. 40, no. 2,
 pp. 27–30, June 2008. Available: http://doi.acm.org/10.1145/1383602.1383628
