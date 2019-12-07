---
title: "MoreProcessorsNotAlwaysBetter"
date: 2019-12-06T14:17:02-05:00
cs2013: ["PD_ParallelFundamentals", "PD_ParallelDecomposition", "PD_ParallelAlgorithms", "PD_ParallelPerformance"]
cs2013details: ["fun_1", "PD_2", "PD_4", "PD_5", "Algo_3", "Algo_4", "Algo_5", "Perf_2"]
tcpp: ["TCPP_Algorithms", "TCPP_Programming", "TCPP_CrossCutting"]
courses: ["CS0", "CS1", "CS2", "DSA", "Systems"]
senses: ["visual", "movement"]
draft: true
---

## Original Author/link

This activity was originally proposed by Mary Smith and Srishti Srivastava. 

[Paper](https://tcpp.cs.gsu.edu/curriculum/sites/default/files/ws_eduhpcp110s2-file1.pdf) (Srivastava2019) and [slides](https://tcpp.cs.gsu.edu/curriculum/sites/default/files/Srishti_Mary_EduHPC_SC2019_Presentation.pdf) 
available on-line.

---

## Details

See paper for details. In summary, the goal is to write the statement 
"More Processors Are Not Always The Best", along with the indices of each letter. 

* Sequential phase. In the sequential phase, a single student is instructed 
  to first write the statement show above (task 1) and then write the index 
  associated with each letter (0 .. 32, 36 if including spaces) underneath (task 2). 
  Another student times how long it takes.

* In the "Uniprocessor multi-tasking phase", the same student is asked to 
  interleve tasks 1 and 2. In other words, they first write a letter, then 
  write an index, then write a letter, and so on. The second student times how 
  long it takes, and compares it to the first result. 

* In the "two process parallel phase", one student completes task 1, while 
  another student completes task 2. A third student times how long it takes, 
  and compares the performance to tasks one and two. 

* In the "multi-processor parallel phase", there are five total students. 
  The first student is assigned to write the phrase "more processors are", 
  the second to writing the phrase "not always the best", and the third 
  student is assigned to write the indices associated student 1's phrase. 
  Student 4, however, must wait until student 3 completes before s/he can 
  start writing his or her set of indices. The fifth student times how 
  long it takes. This scenario is used to demonstrate Amdahl's law.


All together, the activity distinguishes between parallelism and concurrency, 
and introduces the notion of Amdahl's law and speedup.


---
## CS2013 Knowledge Unit Coverage

### PD/Parallel Fundamentals Core Tier 1

1\. Distinguish using computational resources for a faster answer from managing efficient access to a shared resource. [Familiarity]	


### PD/Parallel Decomposition

**Core Tier 1***:
1\. Explain why synchronization is necessary in a specific parallel program. [Usage]

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]

**Core Tier 2**:

4\. Parallelize an algorithm by applying task-based decomposition. [Usage]

5\. Parallelize an algorithm by applying data-parallel decomposition. [Usage]

## PD/Parallel Algorithms, Analysis and Programming

3\. Define "speed-up" and explain the notion of an algorithm's scalability in this regard. [Familiarity]

4\. Identify independent tasks in a program that may be parallelized. [Usage]

5\. Characterize features of a workload that allow or prevent it from being naturally parallelized. [Familiarity]

## PD/Parallel Performance

2\. Calculate the implications of Amdahl's law for a particular parallel algorithm. [Usage]	

---

## TCPP Topics Coverage

### Programming Topics 

* Know Tasks and threads: Understand what it means to create and assign work to threads/processes in a parallel program, and know of at least one way do that.

* Comprehend Computation (decomposition strategies): Understand different ways to assign computations to threads or processes

* Comprehend Performance Metrics (Speedup): Understand how to compute speedup, and what it means

* Know Performance Metrics (Amdahl's Law): Know that speedup is limited by the sequential portion of a parallel program, if problem size is kept fixed


### Algorithm Topics 

* Comprehend Time: Recognize time as a fundamental computational resource that can be influenced by parallelism.

* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling)

* Comprehend/Know Scalability in algorithms and architectures: Comprehend via several examples that having access more processors does not guarantee faster execution --- the notion of inherent sequentiality

* Apply Scheduling (Dependencies): Observe how dependencies constrain the execution order of subcomputations --- thereby lifting one from the limited domain of "embarrassing parallelism" to more complex computational structures

* Know Dependencies: Understand the impacts of dependencies 

### Cross Cutting and Advanced Topics 

* Know Concurrency: The degree of inherent parallelism in an algorithm, independent of how it is executed on a machine.



---

## Recommended Courses

* **CS0/CS1/CS2**: The authors of the activity presented the activity to
  students in CS0, CS1, and CS2 at several institutions.

* **DSA**: In addition to CS2, TCPP recommends notion of threads, computation,
   dependencies be covered in either DSA or Systems. 

* **Systems**: In addition to CS2 and DSA, TCPP recommends notation of threads 
   and dependencies be covered in Systems courses.

---

## Accessibility

The activity requires vision and potentially some movement. If writing is 
being done somewhere central, students who have mobility issues may find 
participating in the writing components difficult. 

However, mobility-challenged students may be able to participate by being 
in the role of the student who times the tasks.  A blind student can also 
fill this role by pressing a stop watch when an instructor says "go", and 
stopping the timer when the instructor says "time". The instructor can then 
read out-loud how much time had elapsed.

---


## Assessment 

Paper (Srivastava2019) performs assessment on this activity and another 
activity (FindOldestPenny). For this particular activity, 
assessment was performed on 102 students (77 male, 25 female) over four 
institutions. The vast majority (83.3%) were aged 18-22. In addition, 
29 students were Freshmen, 29 were sophomores, 26 were juniors, and 18 
were seniors. Students were given the ASPECT survey that measures student 
engagement related to three constructs (value of activity, instructor 
contribution, and personal effort). Statistial significance was measured 
using a combination of one-way and two-way ANOVA tests. While no statistical 
difference was discovered for any of the three constructs over age or gender, 
Juniors had a statistically greater value of the activity over Freshmen, and
Juniors had a statistically significant greater sense of instructor 
contribution than Freshmen or Sophomores. The authors suggest that 
that younger students may be more used to active learning strategies
from K-12, while it may be more novel for older college students.

---

## Citations

* S. Srivastava, M. Smith, A. Ghimire, and S. Gao, "Assessing the integration of
  parallel and distributed computing in early undergraduate computer science
  curriculum using unplugged activities", in _Proceedings of the Workshop on
  Education for High Performance Computing (EduHPC'19)_, 2019, _to appear_.
  [Online]. Available: https://tcpp.cs.gsu.edu/curriculum/sites/default/files/ws_eduhpcp110s2-file1.pdf

* M. Smith and S. Srivastava, "Evaluating student engagement towards 
  integrating parallel and distributed computing (PDC) topics in undergraduate 
  level computer science curriculum", in _Proceedings of the 50th ACM 
  Technical Symposium on Computer Science Education (SIGCSE'19)_. 2019, 
  pp. 1269–1269. [Online, Abstract Only]. Available: http://doi.acm.org/10.1145/3287324.3293854



