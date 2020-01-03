---
title: "FindOldestPenny"
date: 2019-12-06T13:09:20-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms", "PD_ParallelPerformance"]
cs2013details: ["PD_2", "Algo_4", "Perf_1", "Perf_2"]
tcpp: ["TCPP_Algorithms", "TCPP_Programming"]
tcppdetails: ["C_decomposition", "C_LoadBalancing", "K_Amdahl", "C_Scaling", "K_Selection"]
courses: ["CS0", "CS1", "CS2", "DSA", "Systems"]
senses: ["touch", "visual"]
medium: ["coins"]
---

## Original Author/link

This activity was originally proposed by Mary Smith and Srishti Srivastava,
with consultation from Brett A Becker. 

[Paper](https://tcpp.cs.gsu.edu/curriculum/sites/default/files/ws_eduhpcp110s2-file1.pdf) (Srivastava2019) and [slides](https://tcpp.cs.gsu.edu/curriculum/sites/default/files/Srishti_Mary_EduHPC_SC2019_Presentation.pdf) 
available on-line.

### Similar Activities

[FindSmallestCard]({{<ref "activities/findsmallestcard">}}), [FindYoungestStudent]({{<ref "activities/findyoungeststudentinclass">}})

---

## Details

See paper for details. In summary, the goal is to find the oldest penny in a 
pile of pennies. This is first done sequentially, with one student trying 
to determine the oldest penny in a group of 50 pennies. Next, two students are 
employed, with each student getting a bag of 25 pennies. Lastly, four 
students get two pennies each, while a fifth student gets 42 pennies. This 
last scenario indicates the importance of load-balancing, and Amdahl's Law. 

This activity is very similar to FindYoungestStudentinClass proposed by 
Chitra P (Chitra2019)

---

## CS2013 Knowledge Unit Coverage


### PD/Parallel Decomposition Core Tier 1

2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]

### PD/Parallel Algorithms Core Tier 2

4\. Identify independent tasks in a program that may be parallelized. [Usage]

### PD/Parallel Performance

1\. Detect and correct a load imbalance. [Usage]

2\. Calculate the implications of Amdahl's law for a particular parallel algorithm [Usage]

---

## TCPP Topics Coverage

### Programming Topics

* Comprehend Computation Decomposition Strategies: Understand different ways to assign computations to threads or processes.
* Comprehend Load balancing: Understand the effects of load imbalances on performance, and ways to balance load across threads or processes.
* Know Amdahl's Law: Know that speedup is limited by the sequential portion of a parallel program, if problem size is kept fixed

### Algorithms Topics

* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling)
* Know Selection: Observe algorithms for finding order statistics, notably min and max. Understand that selection can always be accomplished by sorting but that direct algorithms may be simpler. (0.5 hours)

---

## Recommended Courses

* **CS0/CS1/CS2**: The authors of the activity presented the activity to 
  students in CS0, CS1, and CS2 at several institutions.  
* **DSA**: In addition to CS2, TCPP recommends that computation, performance and selection topics 
  be covered in DSA.
* **Systems**: In addition to DSA, TCPP recommends that load balancing be covered in Systems. 

---

## Accessibility

This activity may be difficult for students who are blind. For those students, 
the similar activity by Chitra P ([FindYoungestStudent]({{<ref "activities/findyoungeststudentinclass">}})) may be a better choice.

---


## Assessment 

Paper (Srivastava2019) performs assessment on this activity and another 
activity ([MoreProcessorsNotAlwaysBetter]({{<ref "activities/moreprocessorsnotalwaysbetter">}})). For this particular activity, 
assessment was performed on 98 students (73 male, 25 female) over four 
institutions. The vast majority (81.6%) were aged 18-22. In addition, 
38 students were Freshmen, 18 were sophomores, 25 were juniors, and 17 
were seniors. Students were given the ASPECT survey that measures student 
engagement related to three constructs (value of activity, instructor 
contribution, and personal effort). Statistial significance was measured 
using a combination of one-way and two-way ANOVA tests. While no statistical 
difference was discovered for any of the three constructs over gender or year 
in college, 23-27 year-olds had a statistically greater value of the activity and sense 
of instructor contribution than 18-22 year olds. The authors suggest that 
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

