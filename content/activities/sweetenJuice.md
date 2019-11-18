---
title: "SweetenJuice"
date: 2019-11-07T11:07:01-05:00
tags: ["PD_ParallelDecomposition", "PD_CommunicationAndCoordination", "TCPP_Programming", "TCPP_Algorithms", "TCPP_CrossCutting", "K-12", "CS2", "DSA", "Systems", "movement"]
draft: true
---

## Original Author/link

Originally described by Mordechai Ben-Ari and Yifat Ben-David Kolikant (Ben-Ari1999)

No web-link to independent description available. See paper (Ben-Ari1999) for 
additional details.

---

## Details

The paper uses dramatizations to help students understand algorithmic execution.
The paper only describes one such lesson, which is used to introduce the 
concept of mutual exclusion. The following is a rough summar of the exercise 
in (Ben-Ari1999):

Two students volunteer to be robots. A drinking glass is placed at a visible 
point in the classroom, purporting to contain "juice". 
The door (or another portion of the classroom) is denoted as the kitchen. 
In the "kitchen" area, there is a pile of wooden/plastic 
cubes (or balls) that will represent "sugar cubes" in this exercise. 

The goal is to sweeten the juice by adding exactly one sugar cube to the glass.

### Initial algorithm
The student "robots" are then asked to execute the following algorithm:

```
taste the juice (i.e. pick up the glass and look at it)
if the juice is not sweet then:
    go to the kitchen
    take a sugar cube
    come back to the table
    add the sugar cube to the juice
```

This is repeated several times to show there are instances when two sugar cubes 
are added to the glass. 

During the classroom discussion, students are asked a number of questions:

* Does the algorithm produce the same result every time (number of sugar cubes in the glass)? 

* Does the algorithm produce the desired result ever time (one sugar cube in the glass)?

The notion of "correctness" is then introduced: an algorithm is considered 
correct if it performs as specified in every scenario.

To prove that an algorithm is _incorrect_, it requires only one contradicting 
scenario.

### Correcting the algorithm
Next, students are asked to modify the algorithm to make it correct. Every 
time a new algorithm is presented, students dramatize it out, and produce a 
contradicting scenario. The students are made to release that with the 
current tools they have, they cannot create a "correct" algorithm.

Mutual exclusion can then be introduced. 

**Suggeted Variation:**

To introduce mutual exclusion, we suggest introducing a wooden block (or box) 
as a new prop. The block is originally on a chair near the table which the 
glass is on. 

* When a student robot reaches a table, he or she immediately puts the 
  block on the table, until they are finished with whatever activity they are 
  doing at the table. Once they are done, they put the block back on the chair, 
  and leaves.

* Every student robot who comes to the table must check to see if there is a 
  block on the table. If so, they cannot come to the table, and must instead 
  wait. If there is no block, they can proceed to the table. 

The students should attempt to come up with an algorithm using the wooden block 
as an additional prop, and once again evaluate their algorithm for correctness.
They should see that using mutual exclusion enables the creation of a correct 
algorithm.  

---
## CS2013 Knowledge Unit Coverage

### Parallel Decomposition (Core Tier 1)

1\. Explain why synchronization is necessary in a specific parallel program. [Usage]

### Communication and Coordination (Core Tier 1, Core Tier 2)

1\. **Core Tier 1**: Use mutual exclusion to avoid a given race condition. [Usage]

2\. **Core Tier 1**: Give an example of an ordering of accesses among concurrent activities (e.g., program with a data race) that is not sequentially consistent. [Familiarity]

5\. **Core Tier 2**: Write a program that correctly terminates when all of a set of concurrent tasks have completed. [Usage]

8\. **Core Tier 2**: Write a test program that can reveal a concurrent programming error; for example, missing an update when two activities both try to increment a variable. [Usage]



---

## TCPP Topics Coverage

### Programming Topics

* Apply Synchronization (Critical regions): Be able to write shared memory 
  programs that use critical regions for synchronization.

* Know Concurrency Defects (Data Races): Know what a data race is, and how to 
  use synchronization to prevent it.

### Algorithm Topics

* Know Synchronization: Be aware of methods for controlling race conditions.

### Cross-Cutting and Advanced Topics

*  Know Non-determinism: Different execution sequences can lead to different 
   results hence algorithm design either be tolerant to such phenomena or be 
   able to take advantage of this.
 
---

## Recommended Courses


* **K-12**: The authors used dramatizations in a high school course, which 
  suggests that the acitivity is appropriate for K-12 students.

* **CS2/DSA/Systems** TCPP recommends that programming topics such as 
  synchronization can be taught as early as CS2, and is also appropriate for 
  DSA and Systems courses. Topics such as data races and non-determinism may 
  be most appropriate for DSA or systems courses.

---

## Accessibility

The original description in (Ben-Ari1999) seems to recommend an actual glass 
of juice. However, we recommend that fake sugar cubes and an empty drinking 
glass be used instead. Otherwise, the activity might lead to spills, or be 
difficult for students with diabetes or other metabolic issues to participate.


---


## Assessment 

(Ben-Ari1999) ran the dramatizations with high school students. The authors 
note that while students were originally "embarassed" by the dramatizations 
and thought htey were "stupid", they eventually came to regard them as 
being central to their understanding of algorithms. Main result is that 
over the course of term, students began to appreciate the importance of 
correctness and its essentiality in algorithm design.

---

## Citations

* M. Ben-Ari and Y. B.-D. Kolikant, "Thinking parallel: The process of 
  learning concurrency", in *Proceedings of the 4th Annual SIGCSE/SIGCUE 
  ITiCSE Conference on Innovation and Technology in Computer Science Education*, 
  ser. ITiCSE ’99. New York, NY, USA: ACM, 1999, pp. 13–16. 
  Available: http://doi.acm.org/10.1145/305786.305831
