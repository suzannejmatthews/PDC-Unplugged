---
title: "SieveOfErastothenes"
date: 2019-11-04T10:56:26-05:00
cs2013: ["PD_ParallelDecomposition"]
tcpp: ["TCPP_Programming"]
courses: ["CS2", "DSA", "ProgLang"]
senses: ["movement", "visual"]
draft: true
---

## Original Author/link

Originally Described by Michelle Moore (Moore2000)

No web-link to independent description available. See paper (Moore2000) for 
additional details.

---

## Details

Moore describes an example exercise that she presents in a parallel processing 
lab to illustrate data parallelism. Originally, the exercise is meant to 
distinguish between task parallelism and data parallelism; however, the task 
parallelism component is a bit weak, and so is not included here.

Prior to the start of the exercise, the instructor starts by writing as many 
integers as possible on the board (1-30 is recommended at the very least). To 
illustrate the data parallel model:

* students are selected to be processors, and the *n* values are divided amongst 
  the *s* students, so that each student has a partition of *n/s* of the data.

* Each student processor then marks the numbers in its portion of data that are divisible by 2, 3, 5, etc.



---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition (Core Tier 2)

5\. Parallelize an algorithm by applying data-parallel decomposition.

---

## TCPP Topics Coverage

### TCPP Programming Topics

* Apply Data parallel: Be able to write a correct data parallel program for shared-memory machines and get speedup, should do an exercise.


---

## Recommended Courses

* Moore covers the concept in a parallel processing lab, though it is not 
  clear which course the lab was used in.

* **CS2/DSA/ProgLang** - TCPP recommends that data parallelism can be taught 
  in either CS2, DSA or programming languages.

---

## Accessibility

Since this activity requires students to mark values on a board in front of 
the classroom, it may be challenging for mobility-impaired students or blind 
students.

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

