---
title: "ParallelRadixSort"
date: 2019-11-14T10:30:47-05:00
cs2013: ["PD_ParallelDecomposition"]
tcpp: ["TCPP_Algorithms"]
courses: ["K-12", "CS2", "DSA"]
senses: ["visual", "movement"]
draft: true
---

## Original Author/link

Originally Described by Adam Rifkin (1994). No web-link to independent 
description available. However, (Sivilotti2003) employed the exercise in a 
summer workshop for middle school girls, and provided a write-up of the 
activity and slides associated with the activity at 
[his website](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/)

* Slides (includes other activities) [PPT](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/fesc.ppt)
* 1 Page Synopsis [PDF](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/parallel.pdf)


See papers (Rifkin1994, Sivilotti2003) for additional details. 




---

## Details

(Rifkin1994) designed the activity to take place in the course of the hour, 
and was introduced to high school minority students in a workshop format.
Prior to the exercise, students are given an overview of the concept of 
sorting, and try to come up with ways to sort a collection of six random 
numbers.

The instructor then splits the group into nine teams (of about the same size), 
with three teams assigned to a separate supervisor. The supervisor will then 
have one of the three teams perform bubble sort, the second perform 
odd-even-transposition sort (described in a separate exercise), and the last 
perform parallel radix sort.

Each team under the care of supervisor stands in a separate row. 
Each row has indices noted on the ground, indicating where students should 
stand, numbered from 0 … n-1 where n is the number of students in each row. 
Each student at index i is handed a random number that corresponds to the 
same index in a separate row. Each row is then given its own set of 
instructions, and they are instructed to follow the instructions specifically 
(without talking) to sort the numbers.

For parallel radix sort, the exercise is formed as a "race", where the group 
leader walks down the line with the student at space 0. 

* The student at space 0 (or "roving student"), as they walk, reveals their 
  number to the other students standing in place. 
* Students standing in place ("stationary students") keep track of a private 
  counter (which starts at 0). Whenever a stationary student sees a number 
  walk  pass that is _less_ than their number, they increment their counter by 
  one. 
* As  the roving student passes by each stationary student, the stationary 
  student "acknowledges" the fact that they've seen the number by rasiing 
  their hand, enabling the roving student to go to the next spot. 
* Once the roving student reaches the end of line, he or she returns to space 0. 
  The student at space 1 then becomes the roving student, while all other 
  students remain stationary. Starting at space 0, they walk down the line, 
  revealing their numbers to each stationary student, who raises their hand 
  in acknowledgement, and updates their private counters as needed. 
* The process continues until every student had an opportunity to walk down 
  the line. 
* Once everyone had the opportunity to walk down the line, the group leader 
  indicates that everyone should simultaneously leave the space they were 
  standing and go to the same space indicated by their private counter. After 
  doing this, the numbers should be now be sorted. 

The smallest number will have had a private counter of 0, and will stand 
in space 0, as they never encountered a number that was smaller. The next 
smallest number will be at space 1, and so forth. 

Students are asked to think why the list should be sorted at the end of 
Parallel Radix Sort. 

### Variants (Sivilotti2003)
Sivilotti performed the activity exactly as described in (Rifkin1994). However,
prior to introducing the activity, used an analogy to describe computers as
"chefs" and programs to "recipes". Like programs, recipes are characterized
by what their ingredients (input) and the final product (output). A software
engineer is thus described as a "recipe-engineer".

---
## CS2013 Knowledge Unit Coverage

### Parallel Decomposition
2\. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]


---

## TCPP Topics Coverage

### TCPP algorithms

* Comprehend Asymptotics: Understand upper (big-O) and lower bounds 
  (big-Omega,); follow elementary big-O analyses, e.g., the O(log n) 
  tree-depth argument for mergesort with unbounded parallelism.

* Comprehend Time: Recognize time as a fundamental computational resource that 
  can be influenced by parallelism.

* Comprehend Speedup: Recognize the use of parallelism either to solve a given 
  problem instance faster or to solve larger instance in the same time 
  (strong and weak scaling).

* Know Sorting: Observe several sorting algorithms for varied platforms - 
  together with analyses. Parallel merge sort is the simplest example, 
  but equally simple alternatives for rings and meshes might be covered also; 
  more sophisticated algorithms might be covered in more advanced courses.

---

## Recommended Courses

* **K-12**: (Rifkin1994) successfully introduced sorting concepts to minority 
  high school students in a sumemr workshop. (Sivilotti2003) successfully 
  introduced the activity to middle school girls in a 45-minute format.

* **CS2/DSA**: TCPP recommends that topics of sorting can be covered as early 
  as CS2, and that both sorting and algorithmic complexity topics are 
  appropriate for DSA.

---

## Accessibility

The exercise may be difficult for students who are mobility-impaired, or have 
trouble with visual. Cards can have Braille on them, so when a blind student 
plays the stationary student role, he or she can reach out and touch the card 
to read the value. Verbal acknowledgements may be most appropriate when the 
blind student acts as the roving student in the exercise. Verbal 
acknowledgements may also be preferable to students who have trouble raising 
their hands.
 
---


## Assessment 

(Rifkin1994) gives a general overview of assessment; 81 students completed 
surveys, in which they overwhelmingly responded that the workshop as a whole 
was a positive experience, and that respondents “learned something, had fun, 
and had a better impression of computer science” (Rifkin1994). However, 
specific assessment of parallel radix sort was not provided.

(Sivilotti2003) reported the sorting activity could be completed in a 45 minute
period. Students were asked a number of questions, including rating the
exercises. On a scale from 1 (low) to 5 (high) students rated the parallel
sorting exercise as a 4.4. Students also made statements such as "the more
'chefs'[processors] you use, the faster the program will finish" and "sequentia$
are slow" (Sivilotti1999). Students were also asked to evaluate the overall
quality of the computer science module on scale of 1 (low) to 5 (high), and
rated the cs component of the workshop as 4.6. Note that this includes other
activities.

---

## Citations

* P. A. G. Sivilotti and M. Demirbas, "Introducing middle school girls to
  fault tolerant computing", in *Proceedings of the 34th SIGCSE Technical
  Symposium on Computer Science Education (SIGCSE ’03)*. New York, NY, USA:
  ACM, 2003, pp. 327–331, [Online]: http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/
  Available: http://doi.acm.org/10.1145/611892.611999

* A. Rifkin, "Teaching parallel programming and software engineering concepts 
 to high school students", In *SIGCSE Bulletin*, vol. 26, no. 1. and 
 *Proceedings of the Twenty-fifth SIGCSE Symposium on Computer Science 
 Education*, 1994, pp. 26–30. Available: http://doi.acm.org/10.1145/191033.191044
