---
title: "NondeterministicSorting"
date: 2020-01-06T13:39:13-05:00
courses: ["CS2", "DSA", "Systems", "ParProg", "Graduate"]
cs2013: ["PD_FormalModels"]
cs2013details: ["Formal_6"]
tcpp: ["TCPP_Algorithms", "TCPP_CrossCutting"]
tcppdetails: ["K_Sorting", "K_NonDeterminism"]
senses: ["visual", "movement"]
medium: ["roleplay", "cards"]

---

## Original Author/link

Originally described by Paulo A.G. Sivilotti and Scott Pike

[Paper](http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/sigcse07.pdf) and [poster](http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/nae-fee2010_poster.pdf) available online:

---

## Details

See paper and poster for full details. A high level summary is provided below:

* A group of students are chosen to represent elements in an array. Each student is given a sign/sticker that indicates their position in the array. Each student is also given an index card with a random integer value on it.

* When the instructor says "go", students mill about, comparing index cards with each other. If the other student's index card is out of order with respect to their position in the array (e.g., if the goal is to sort from smallest to largest, and if someone at a lower index has a index card whose value is higher than yours), then the students swap index cards. 

* When each student believes that the array is sorted they raise their hands. When all the students' hands are raised, the students line up according to their positions of the array and display their index cards. The array should be sorted.

**Learning Objectives**
The paper states that the activity has the following learning objectives:

* Deterministic, sequential algorithms are often an over-specification of a non-determistic sorting algorithm. 

* Every execution of the non-determistic algorithm yields a sorted array.

* Good metrics (for termination) are not always obvious 

* An action system terminates when it reaches a fixed point.

**Tips from the authors**
* Ensure that students cannot see other people's index cards from far away; otherwise, they may make implicit comparisons.

* Arrays that are too large take too long to complete. Suggest limiting to 10-15 students for the activity.

---

## CS2013 Knowledge Unit Coverage

## Formal Models and Semantics

6\. Decide if a specific execution is linearizable or not.

---

## TCPP Topics Coverage

### Algorithms Topics
* Know Sorting: Observe several sorting algorithms for varied platforms --- together with analyses. Parallel merge sort is the simplest example, but equally simple alternatives for rings and meshes might be covered also; more sophisticated algorithms might be covered in more advanced courses 

### Cross cutting and Advanced Topics

* Know Non-determinism: Different execution sequences can lead to different results hence algorithm design either be tolerant to such phenomena or be able to take advantage of this.


---

## Recommended Courses

The instructors used this activity in an upper-level undergraduate course on parallel programming. They also recommend the activity for graduate students.

* **CS2/DSA**: TCPP recommends that sorting concepts that covered in CS2 and/or DSA.
* **Systems**: In addition to DSA, TCPP recommends that non-determinism can be presented in a systems course.

---

## Accessibility

This activity may be difficult for students who are mobility challenged or have low vision. To assist students in the latter category, we suggest that cards 
be purchased that have visible numbers and Braille. 

---


## Assessment 

No assessment provided. 

---

## Citations

* P. A. G. Sivilotti and S. M. Pike, "The suitability of kinesthetic learning activities for teaching distributed algorithms", in _Proceedings of the
  38th SIGCSE Technical Symposium on Computer Science Education (SIGCSE'07)_, 2007, pp. 362–366.
  Available Online: http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/sigcse07.pdf. Also: http://doi.acm.org/10.1145/1227310.1227438

* P. A. G. Sivilotti, "Kinesthetic learning activities in an upper-division computer science course", in _National Academy of Engineering Frontiers
  of Engineering Education symposium_, 2010, _poster_; http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/nae-fee2010_poster.pdf