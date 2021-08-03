---
title: "ArrayAddition"
date: 2020-01-07T15:13:49-05:00
cs2013: ["PD_ParallelFundamentals", "PD_ParallelDecomposition", "PD_CommunicationAndCoordination", "PD_ParallelAlgorithms"]
cs2013details: ["Fun_2", "PD_1", "PD_2", "CAC_1", "CAC_2", "CAC_5", "CAC_8", "Algo_4"]
tcpp: ["TCPP_Programming"]
tcppdetails: ["A_SharedMemory", "A_DataParallel", "A_CriticalRegions", "C_DataRaces"]
courses: ["K_12", "CS2", "DSA", "Systems", "ProgLang"]
senses: ["visual", "movement"]
medium: ["boardwork", "paper", "cards", "pens"]

---

## Original Author/link

Originally described by Robert Chesebrough and Ivan Turner; the authors cite the 2nd chapter of James Reinders' book (see citations) as inspiration for this example.

No link to indepdendent description available. Please see Details section for more information.

---

## Details

Students sitting at desks represent "threads" on individual cores. Each student has a piece of paper on their desk representing local memory. Prior to the activity, the instructor writes an array on the board, filled with random values (limit 1 through 10 for ease of addition), with indices written underneath. The goal is to, as a class, add up all the elements in the array and update a global sum value written on a index card held by the instructor.

### Naive Case

* As each student sums up their component of the array, they should raise their hand so that the instructor can tell them what is currently on the index card. 

* When the student thinks they know what the new value on the index card should hold, they should raise their hand again and tell the instructor what they think the value should be. The instructor should then overwrite what is on the index card with the value that the student tells them. 

* When each student is "done", they should give a thumbs up.

* When all students are done, the instructor should read the value on their index card. Most likely the value is wrong (if this does not happen, as a student is adding to the total, surreptitiously update it with another students total; this will cause an accidental overwrite of a value). 

* There are a few strategies that can play out -- the student queries the instructor with every number they are adding, or they do a local sum entirely on their own, and only convey the total to the instructor. In both cases, it is likely that values are lost.

* Have a discussion on what went wrong -- this leads nicely into discussing data races. 


### Defining Critical Regions

* To fix the issue, the instructor places on a table in front of the class a special pen. Whoever has the pen has sole access to the instructor and the instructor's index card until they put the pen down. 

* Using this method, each student individually updates the global index card with their sums, and the index card should contain the proper sum of all the elements in the array.

* However, students observe a substantial performance impact from using the "critical section"


### Using Reduction

* In addition to their piece of paper that is local memory, students are given a special index card that represents a partial sum variable. 

* As before, student should add up the values assigned to them. When they are done, they should write their total on the partial sum variable card and give a "thumbs up" sign to indicate that they are done.

* When each student gives a thumbs up, the instructor (acting as a "boss" process) gathers all the partial sum cards and adds them together, updating the global index sum card by his or herself. 

* Students should observe that this is more efficient that the critical section approach, but still results in no race conditions.  



---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Fundamentals

2\. Distinguish multiple sufficient programming constructs for synchronization that may be inter-implementable but have complementary advantages. 


### PD/Parallel Decomposition

1\. Explain why synchronization is necessary in a specific parallel program. [Usage]

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]

### PD/Communication and Coordination

1\. Use mutual exclusion to avoid a given race condition. [Usage]

2\. Give an example of an ordering of accesses among concurrent activities (e.g., program with a data race) that is not sequentially consistent. [Familiarity]

5\. Write a program that correctly terminates when all of a set of concurrent tasks have completed. [Usage]

8\. Write a test program that can reveal a concurrent programming error; for example, missing an update when two activities both try to increment a variable. [Usage]

### PD/Parallel Algorithms, Analysis and Programming

4\. Identify independent tasks in a program that may be parallelized. [Usage]


---

## TCPP Topics Coverage

### Programming Topics

* Apply Shared Memory: Be able to write correct thread-based programs (protecting shared data) and understand how to obtain speed up. 

* Apply Data parallel: Be able to write a correct data parallel program for shared-memory machines and get speedup, should do an exercise. Understand relation between different notations for data parallel: Array notations, SPMD, and parallel loops. Builds on shared memory topic above

* Apply Critical regions: Be able to write shared memory programs that use critical regions for synchronization

* Comprehend Data Races: Know what a race condition is, and how to use synchronization to prevent it

---

## Recommended Courses

* **K-12**: The authors shared the described unplugged activities with high school students. 

* **CS2/DSA/ProgLang**: TCPP recommends that shared memory and data parallel concepts be covered in CS2/DSA and Programming Languages.

* **Systems**: In addition to CS2 and DSA, TCPP recommends that critical sections be covered in systems. TCPP also recommends that data races be covered in Systems in adddition to DSA.

---

## Accessibility

This activity is highly visual and involves some movement. The critical section demonstration may be difficult for students who are mobility challenged. In addition, this activity may be difficult for blind students.


---


## Assessment 

(Chesebrough2010) used unplugged activities as part of a larger three-day workshop for 16 high schoool students at Brookyn Tech in summer 2009. Chesebrough and Turner report that "the best part" of the camp was the role playing, and that the exercises helped drive concepts home. However, some of the more advanced students felt that the activities were "childish". However younger and/or less-experienced students enjoyed the role playing exercises.

If all students can see the global index card, it is possible for them to implictly avoid race conditions and fail to produce one, and determine that a core should just "know" what the value is. A short script may be helpful to ensure that students understand what they need to do and what can be assumed (and not assumed).


---

## Citations

* R. A. Chesebrough and I. Turner. "Parallel computing: at the interface of high school and industry". In _Proceedings of the 41st ACM technical symposium on Computer science education (SIGCSE'10)_. pp. 280–284. Available: https://doi.org/10.1145/1734263.1734361
