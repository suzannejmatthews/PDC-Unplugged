---
title: "OddEvenTranspositionSort"
date: 2019-11-04T08:25:13-05:00
cs2013: ["PD_ParallelDecomposition"]
cs2013details: ["PD_2"]
tcpp: ["TCPP_Algorithms"]
tcppdetails: ["C_Asymptotics", "C_Time", "C_Scaling", "K_Sorting"]
courses: ["K-12", "DSA", "CS2"]
senses: ["visual", "movement" ]

---

## Original Author/link

Originally Described by Adam Rifkin (Rifkin1994), with a separate 
description by Michelle Moore (Moore2000). (Bachelis1994) also presents the 
sort as a "compare-exchange sort". We extrapolate on (Rifkin1994), since 
it is well described.

No web-link to independent description available. However, (Sivilotti2003) 
employed the exercise in a summer workshop for middle school girls, and 
provided a write-up of the activity and slides associated with the 
activity at [his website](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/):

* Slides (includes other activities) [PPT](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/fesc.ppt)  
* 1 Page Synopsis [PDF](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/parallel.pdf)


See papers (Rifkin1994, Bachelis1994, Moore2000, Sivilotti2003) for additional details.

### Similiar Exercises: 

Sorting: [parallelRadixSort]({{<ref "activities/parallelradixsort">}}), [sortingNetwork]({{<ref "activities/sortingnetwork">}}) [CardSorting]({{<ref "activities/cardsorting">}})

### Other activities by authors
Rifkin1994: [parallelRadixSort]({{<ref "activities/parallelradixsort">}})

(Bachelis1994): [ParallelAddition]({{<ref "activities/paralleladdition">}}), [FindSmallestCard]({{<ref "activities/findsmallestcard">}}), [CardSorting]({{<ref "activities/findsmallestcard">}}),
  [SieveOfErastothenes]({{<ref "activities/sieveoferastothenes">}})

(Moore2000): [SieveOfErastothenes]({{<ref "activities/sieveoferastothenes">}}), [CardSorting]({{<ref "activities/cardsorting">}}), [MatrixAddition]({{<ref "activities/matrixaddition">}})

---

## Details

(Rifkin1994) designed the activity to take place in the course of the hour, 
and was introduced to high school minority students in a workshop format.  
Prior to the exercise, students are given an overview of the concept of 
sorting, and try to come up with ways to sort a collection of six random 
numbers. 

The instructor then splits the group into nine teams (of about the same size), 
with three teams assigned to a separate supervisor. The supervisor will 
then have one of the three teams perform bubble sort, the second perform 
odd-even-transposition sort, and the last perform parallel radix sort 
(described in a separate exercise). 

Each group under the care of supervisor stands in three rows. Each row has 
indices noted on the ground, indicating where students should stand, numbered 
from 0 ... _n_-1 where _n_ is the number of students in each row. For 
odd-even-transposition sort, even spots are marked in one color, while odd 
spots are marked in another. 

Each student at index _i_ is handed a random number that corresponds to 
the same index in a separate row.  Each row is then given its own set of 
instructions, and they are instructed to follow the instructions specifically 
(without talking) to sort the numbers. 

The row in charge of odd-even-transposition sort performs the following set of 
steps:
* During the "even" phase, neighbors standing on the same colored spaces 
  denoting "even" compare their numbers to their neighbors on the left. If 
  their neighbor is less than them, they swap spaces with their neighbor. 

* During the "odd" phase, neighbors standing on the same colored spaces denoting 
  "odd" compare their numbers with their neighbor to the left. If their 
   neighbor's number is less than them, they swap places with their neighbor.

Students are asked note that the round does not need to be coordinated by 
group leaders, and to observe that that the list was becoming "more sorted" 
with each phase. At the end of the exercise, students were asked to consider 
the strengths and weaknesses of Odd-even-transposition sort, and why it was 
 a parallel algorithm, and how it compares to bubble sort. 

### Variants 

#### (Moore2000)
(Moore2000) describes an example exercise that she presents in a parallel processing 
lab. It is assumed that students know about the Bubble Sort algorithm ahead of 
time. Odd Even Transposition Sort is a "parallel" version of bubble sort. In 
this exercise, students are asked to physically simulate the multiple processors 
performing the sort. The main difference from (Rifkin1994) is that students 
stay _stationary_, while _cards_ move around. This variant may be better for 
classrooms with students with impaired mobility. 

* A subset of students stand in line at the front of classroom, and count off to determine 
  if they are odd or even. Each student who is even is marked with a sticker to 
  indicate that they belong to the "even" group. (Note that two colors of 
  stickers can be used in order to ensure that there are no hurt feelings). It 
  is important that "even" and "odd" alternate in the line. 

* Each student is handed an index card with a unique random number written on 
  it. 
 
* During the even phase, all the Evens turn to the left and compare their card 
  with their neighbor. If the neighbor's card number is smaller than the card they are 
  holding, they swap cards.

* During the odd phase, all the Odds turn to their left and comapre their card 
  with their neighbors. If the neighbor's card number is smaller than the card 
  they are holding, they swap cards.

* The above two phases are repeated until the numbers are in order.

* A separate student (not in line) is responsible for tallying the number of 
  times the odd phases and even phases occur. 

The class then has a discussion that Odd-Even Transposition Sort has a parallel 
time complexity O(*n*) when *n* students are used for sorting. In 
contrast, the serial algorithm (bubble sort) has a time complexity of 
O(*n*<sup>2</sup>). 

#### Sivilotti2003

Sivilotti performed the activity exactly as described in (Rifkin1994). However, 
prior to introducing the activity, used an analogy to describe computers as 
"chefs" and programs to "recipes". Like programs, recipes are characterized 
by what their ingredients (input) and the final product (output). A software 
engineer is thus described as a "recipe-engineer". 

---
 
## CS2013 Knowledge Unit Coverage

### Parallel Decomposition

2\.  Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]


---

## TCPP Topics Coverage

### TCPP algorithms

* Comprehend Asymptotics: Understand upper (big-O) and lower bounds
  (big-Omega,); follow elementary big-O analyses, e.g., the O(log n) 
  tree-depth argument for mergesort with unbounded parallelism.

*  Comprehend Time: Recognize time as a fundamental computational resource 
   that can be influenced by parallelism.

* Comprehend Speedup: Recognize the use of parallelism either to solve 
  a given problem instance faster or to solve larger instance in the same 
  time (strong and weak scaling).

* Know Sorting: Observe several sorting algorithms for varied platforms --- 
  together with analyses. Parallel merge sort is the simplest example, but 
  equally simple alternatives for rings and meshes might be covered also; 
  more sophisticated algorithms might be covered in more advanced courses.

---

## Recommended Courses

* Moore covers the concept in a parallel processing lab, though it is not 
  clear which course the lab was used in.

* **K-12**: (Rifkin1994) successfully introduced sorting concepts to minority 
  high school students in a sumemr workshop. (Sivilotti2003) successfully 
  introduced sorting concepts to middle school girls.

* **CS2/DSA**: TCPP recommends that topics of sorting can be covered as 
  early as CS2, and that both sorting and algorithmic complexity topics are 
  appropriate for DSA.



---

## Accessibility

This exercise appears fairly accesible to everyone. For students who are blind, 
the Braille cards are recommended so students can read the number on them. 
For Deaf students the "Odd" "Even" phases can be signified by holding up a 
large sign. We do not anticipate any mobility issues, as students can sit in 
chairs for this exercise, and perform the variant described in (Moore2000). 
However, some groups may choose to use original description in (Rifkin1994) 
to engage higher energy, able students.

---


## Assessment 

(Rifkin1994) gives a general overview of assessment; 81 students completed 
surveys, in which they overwhelmingly responded that the workshop 
as a whole was a positive experience, and that respondents "learned something, 
had fun, and had a better impression of computer science" (Rifkin1994). 
However, specific assessment of odd-even-transposition sort was not provided. 

(Moore2000) discusses the impact of the parallel computing labs in her course. In general, students 
responded to the labs positively, and felt that labs increased their knowledge 
significantly.

(Sivilotti2003) reported the sorting activity could be completed in a 45 minute 
period. Students were asked a number of questions, including rating the 
exercises. On a scale from 1 (low) to 5 (high) students rated the parallel 
sorting exercise as a 4.4. Students also made statements such as "the more 
'chefs'[processors] you use, the faster the program will finish" and "sequential programs 
are slow" (Sivilotti1999). Students were also asked to evaluate the overall 
quality of the computer science module on scale of 1 (low) to 5 (high), and 
rated the cs component of the workshop as 4.6. Note that this includes other 
activities.  

---

## Citations

* A. Rifkin, "Teaching parallel programming and software engineering concepts 
  to high school students", In *SIGCSE Bulletin*, vol. 26, no. 1. and 
  *Proceedings of the Twenty-fifth SIGCSE Symposium on Computer Science 
  Education*, 1994, pp. 26–30. Available: http://doi.acm.org/10.1145/191033.191044

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.

* M. Moore, "Introducing parallel processing concepts", *J. Comput. Sci. Coll.,* 
  vol. 15, no. 3, pp. 173–180, Mar. 2000. Available: http://dl.acm.org/citation.cfm?id=1852563.1852589

* P. A. G. Sivilotti and M. Demirbas, "Introducing middle school girls to 
  fault tolerant computing", in *Proceedings of the 34th SIGCSE Technical 
  Symposium on Computer Science Education (SIGCSE ’03)*. New York, NY, USA: 
  ACM, 2003, pp. 327–331, [Online]: http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/. 
  Available: http://doi.acm.org/10.1145/611892.611999
