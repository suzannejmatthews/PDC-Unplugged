---
title: "AddLargeNumbers"
date: 2019-12-11T10:46:11-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelAlgorithms"]
cs2013details: ["PD_4", "Algo_4"]
tcpp: ["TCPP_Programming"]
tcppdetails: ["C_Decomposition"]
courses: ["K-12", "CS2", "DSA"]
senses: ["visual"]
draft: true
---

## Original Author/link

Originally described by Gregory F. Bachelis, David A. James, Bruce R. Maxim and Quentin F. Stout (Bachelis1994)

No link to independent description publicly available. Please see details section for a synopsis.

### Other activities by authors

(Bachelis1994): [FindSmallestCard]({{<ref "activities/findsmallestcard">}}), [CardSorting]({{<ref "activities/findsmallestcard">}}), [OddEvenTranspositionSort]({{<ref "activities/oddeventranspositionsort">}}), 
  [SieveOfErastothenes]({{<ref "activities/sieveoferastothenes">}}), [ParallelAddition]({{<ref "activities/paralleladdition">}})

---

## Details

From (Bachelis1994): The goal is to introduce students to how large pairs of numbers in parallel. 

Suppose the goal is to add two large numbers (in this example, 534,789,213 and 495,378,388). The instructor starts by writing the two numbers on the blackboard like so:

```text
  534,789,213
+ 495,378,388
--------------
```

The student "processors" sit facing the blackboard. Each student is assigned a certain set of contiguous digit columns. For example, if there are three students, one student would be assigned the 1s to 100s place, another student would assigned the 1,000 to 100,000 place, and last the 1 million to 100 million place.

Each student is then given an instruction sheet that looks like the following:

```text
1. Add the two _digit numbers from your assigned columns.
2. If the sum requires more than _ digits, tell left neighbor "carry"
3. If your right neighbor says "carry", write "carry" above your total, and add one. 
   If the sum now contains a carry, say "carry" to your left neighbor. 
4. Face right when you are done, and hold up the _ digit answer to the blackboard.
```

Consider the case of 3 student processors. The two large numbers shown in our earlier example will then be split up as follows amongst the three students (student desk positions are also shown):

```text
 | 534 | 789 | 213 |
 | 495 | 378 | 388 |
 [stu2][stu1][stu0 ]
```

In this example, each student gets assigned 3 digit columns (thus the `_` on their instruction sheet is replaced with the number `3`)

* Student 0 adds `213` and `388` and gets `601`. Since this number is three digits, there isn't a carry operation. Student 0 writes `601` on the paper, holds it up to the instructor, and faces to the right.
* Student 1 adds `789` and `378` and gets `1167`, Since this number is four digits, there is a carry operation. Student 1 tells student 2 that there is a carry. Since Student 1 does not get a carry from 
  Student 0 (student 0 is facing right), Student 1 writes `167` on the paper, holds it up to the instructor, and faces to the right.
* Student 2 adds `534` and `495` and gets `1029`. Since this number is four digits, there is a carry operation. Student 2 should turn to the left and say "carry". 
  Student 2 receives a "carry" message from Student 1, and therefore adds 1 to their total, getting `1030`. Student 2 therefore writes `030` on a piece of paper, holds it up to the instructor and faces right.

 The instructor then writes the total on the board: `1,030,167,601`. Since student 2 said carry, the instructor knows to put a leading 1 to the total.

 The exercise can then be repeated with more students or larger numbers. We note that this exercise can be used to demonstrate overflow (to do so, the instructor just does not place the leading number on the board).

 Students should recognize that in the parallel case, the fact that one person is sending a carry is independent of whether or not a carry is received. A more complex algorithm is also presented in (Bachelis1994), but we omit it here.


---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Decomposition


**Core Tier 2**

4\. Parallelize an algorithm by applying task-based decomposition. [Usage]

### PD/Parallel Algorithms

4\. Identify independent tasks in a program that may be parallelized. [Usage]


---

## TCPP Topics Coverage

### Programming Topics

* Comprehend Computation (decomposition strategies): Understand different ways to assign computations to threads or processes.

---

## Recommended Courses

* **K-12**: (Bachelis1994) recommends introducing concepts to students in a secondary-school mathematics or computer science class.
* **CS2/DSA**: TCPP recommends that decomposition strategies should be covered in CS2 or DSA.

---

## Accessibility

The visual aspect of this activity may make it less accessible for blind students. However. students communicating a message to a blind partner can read their total aloud. The instructor can facillitate passing the total to the next student as necessary.

---


## Assessment 

Unknown.

---

## Citations

* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel algorithms in undergraduate computer science courses (tutorial session)", in _Proceedings of the Twenty-first SIGCSE Technical Symposium 
  on Computer Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. Available: http://doi.acm.org/10.1145/323410.323415
  
* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.
