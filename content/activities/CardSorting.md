---
title: "CardSorting"
date: 2019-11-01T12:39:05-04:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelPerformance"]
cs2013details: ["PD_1", "PD_2", "Algo_3", "Algo_4", "Algo_6", Perf_1", "Perf_2", "Perf_3"]
tcpp: ["TCPP_Algorithms"]
courses: ["CS0", "CS1", "CS2", "DSA"]
senses: ["visual", "touch"]
draft: true
---

## Original Author/link
Originally described by Gregory F. Bachelis, David A. James, Bruce R. Maxim and Quentin F. Stout (Bachelis1994). Also alluded to by Garcia and (Moore2000).

Variation using a deck of playing cards by (Ghafoor2019):

[iPDC Modules](https://www.csc.tntech.edu/pdcincs/index.php/ipdc-modules/)

* Available in [Word](https://www.csc.tntech.edu/pdcincs/resources/modules/unplugged/card_sorting/Card%20Sorting.docx) and [PDF](https://www.csc.tntech.edu/pdcincs/resources/modules/unplugged/card_sorting/Card%20Sorting.pdf)

### Similiar Exercises: 

Sorting: [oddEvenTranspositionSort]({{<ref "activities/oddeventranspositionsort">}}), [ParallelRadixSort]({{<ref "activities/parallelradixsort">}}), [sortingNetwork]({{<ref "activities/sortingnetwork">}}),

### Other activities by authors
(Bachelis1994): [ParallelAddition]({{<ref "activities/paralleladdition">}}), [FindSmallestCard]({{<ref "activities/findsmallestcard">}})

(Moore2000): [SieveOfErastothenes]({{<ref "activities/sieveoferastothenes">}})

(Ghafoor2019):

----

## Details

From (Bachelis1994):
The goal is to sort a deck of 16 cards (it is assumed that there are unique numbers) using parallel selection sort. The notion of a "two-card comparator" is discussed as part of the process (e.g. input is two cards, outputs the smaller of the two cards). The processor therefore employs a series of "two-card comparators" to sort the set of cards. (Bechelis1994) recommends that students are first introduced to the [FindSmallestCard]({{<ref "activities/findsmallestcard">}}) activity.

### Serial case: 

* Students recognize that to find the smallest card in a collection of 16 cards, it should take 15 comparisons. Therefore, to find the next smallest it takes 14 comparisons, then 13, and so on. Therefore 
  _sorting_ 16 cards takes (using Guass' formula) (15 x 16)/2 comparisons. Assuming that each comparison takes 1 unit time, then sorting 16 cards serially requires 120 time steps.
* Ask the students: _how to make the process faster?_ 
* The answer is to to use several processors and a "divide and conquer" methodology.

### Parallel Case

**Two Students**:

* Each student is given 8 cards, and asked to sort using selection sort. (i.e. Find the smallest, then the next smallest, etc.). At the end, the smallest card should be at the top of the deck, and the largest
  should be at the bottom of the deck. 
* The merge step: Once each student has a deck of sorting cards, each student holds up their top most (i.e. "smallest card"). The smaller card then gets put down (face up) in a pile between the two students. 
  The students continue the process, each time with the student with the smaller card putting their card face up on the common pile. At the end, we have one sorted deck of 16 cards.
* Ask the students: _how many time steps did this require?_ 
* Answer: To sort 8 cards, a total of (8 x 7)/2 = 28 comparisons are required. Since each student performed their comparisons simultaneously and in parallel; thus a total of 28 time steps are required. 
  The final merge takes at most 15 comparison steps, for a total of 28 + 15 = 43 time steps. 

**Four Students**:

* Each student is assigned a number (1..4) and is given a subset of 4 cards.
* Each student sorts their four cards. At the end, students 1 and 2 merge their decks, with student 2 receiving the new deck. Likewise, students 3 and 4 merge their decks, with student 4   
  receiving the deck. Lastly, student 2 and 4 merge their decks to create final sorted deck.
* Ask the students: _how many time steps did this require?_
* Answer: Each student initially takes (3 x 4) / 2 = 6 comparisons to sort their decks of four cards. Since the students performed their comparisons simultaneous and in parallel, a total of 6 time steps 
  are needed for this step. Next, the merges between students 1 and 2 happen independently from the merges of students 3 and 4, and therefore can occur in parallel. To merge to a total of 8 cards, 7 comparisons
  (and thus 7 time steps are needed). Lastly, for the final round of merging between students 2 and 4, 15 time steps are needed. Therefore, the total number of time steps is 6 + 7 + 15 = 28 time steps.


**Eight students**

* Each student is assigned a number (1..8) and given a subset of two cards.
* Each student sorts their two cards. Then: Students 1 and 2 merge their decks with student 2 receiving the new deck; Students 3 and 4 merge their decks, with student 4 receiving the new deck; Students 5 and 6 
  merge their decks, with student 6 receiving the new deck; Students 7 and 8 merge their decks, with student 8 receiving the new deck. In the second round of merging, students 2 and 4 merge their decks, with student 4 receiving the deck; students 6 and 8 merge their decks, with stduent 8 receiving the resulting deck. Lastly, students 4 and 8 merge their decks together to produce the final sorted deck.
* Ask the students: _how many time steps does this require?_
* Answer: Each student requires one time step to sort their cards. All the time is now in the merge step. The first round of merging occurs in parallel and produces four decks of four cards. Producing a deck 
  of four cards takes 3 comparisons, and thus this first merge step requires 3 time steps. The second round of merging produces two decks of eight cards; producing a deck of eight cards requires 7 comparisons, 
  and thus the second round of merging requires 7 time steps. The final round of merging 15 steps. Thus, the total time is 1 + 3 + 7 + 15 = 26 time steps. 


The class then should asked to calculate the speedup of the parallel cases over the serial cases. They should be able to recognize that as more processors are added, the merge step starts to require the 
majority of the time.




### Variations
(Ghafoor2019) describes a variation using two standard decks of playing cards, rather than the 16 numbered cards that (Bachelis1994) recommends. There is also no specified sorting algorithm in this variant.

The concept of card sorting is described by (Moore2000). In a parallel 
processing lab, students form groups to develop card sorting algorithms to 
illustrate data parallelism in shared memory, data parallelism in message passing, and task parallelism for message 
passing. However, additional details on *how* exactly this is accomplished is 
not provided.

---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition (Core Tier 1)

1. Explain why synchronization is necessary in a specific parallel program. [Usage]

2. Identify opportunities to partition a serial program into independent parallel modules. [Familiarity]


### PD/Parallel Algorithms, Analysis & Programming - Core Tier 2

3\. Define "speed-up" and explain the notion of an algorithm's scalability in this regard. [Familiarity]

4\. Identify independent tasks in a program that may be parallelized. [Usage]

6\. Implement a parallel divide-and-conquer (and/or graph algorithm) and empirically measure its performance relative to its sequential analog.


### Parallel Performance (Elective)

1. Detect and correct a load imbalance. [Usage]
2. Calculate the implications of Amdahl's law for a particular parallel algorithm (cross-reference SF/Evaluation for Amdahl's Law). [Usage]
3. Describe how data distribution/layout can affect an algorithm's communication costs. [Familiarity]

---

## TCPP Topics Coverage

### Algorithms Topics 
* Know Sorting: Observe several sorting algorithms for varied platforms --- 
  together with analyses. Parallel merge sort is the simplest example, 
  but equally simple alternatives for rings and meshes might be covered also; 
  more sophisticated algorithms might be covered in more advanced courses 
  (1 hour)
* Comprehend Time: Recognize time as a fundamental computational resource that can be influenced by parallelism
* Comprehend Speedup: Recognize the use of parallelism either to solve a given problem instance faster or to solve larger instance in the same time (strong and weak scaling) 
* Apply Scheduling (Dependencies): Observe how dependencies constrain the execution order of subcomputations --- thereby lifting one from the limited domain of "embarrassing parallelism" to more complex 
  computational structures
* Comprehend Divide & conquer (parallel aspects): Observe, via tree-structured examples such as mergesort . . . how the same structure that enables divide and conquer (sequential) algorithms 
  exposes opportunities for parallel computation
---

## Recommended Courses

* **CS0/CS1/CS2** - The authors suggest using the activity in introductory 
  computer science courses. In addition, there is assessment supporting this 
  approach.

* **DSA** - In addition to CS2, TCPP recommends that DSA may be an appropriate 
  place to cover sorting topics.
 
---

## Accessibility

Yes. This activity should be accessible to a wide range of students. The 
activity can easily be done at a table. Blind students can also participate 
in the exercise if Braille playing cards were used.

---


## Assessment 

Unknown. (Moore2000) discusses the impact of the parallel computing labs in 
her course. In general, students responded to the labs positively, and felt 
that labs increased their knowledge significantly.


---

## Citations

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.

* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel algorithms in undergraduate computer science courses (tutorial session)", in _Proceedings of the Twenty-first SIGCSE Technical Symposium 
  on Computer Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. Available: http://doi.acm.org/10.1145/323410.323415

* S. K. Ghafoor, M. Rogers, D. Brown, and A. Haynes, "ipdc modules (unplugged)" 
  last accessed Oct 16, 2019. [Online]. Available: https://www.csc.tntech.edu/pdcincs/index.php/ipdc-modules/

* M. Moore, "Introducing parallel processing concepts", *J. Comput. Sci. Coll.,* 
  vol. 15, no. 3, pp. 173–180, Mar. 2000. Available: http://dl.acm.org/citation.cfm?id=1852563.1852589

