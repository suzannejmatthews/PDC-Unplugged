---
title: "PipelineSort"
date: 2019-12-11T12:38:56-05:00
cs2013: ["PD_ParallelAlgorithms"]
cs2013details: ["Algo_9"]
courses: ["K_12"]
senses: ["touch", "visual"]

---

## Original Author/link

Originally described by Gregory F. Bachelis, David A. James, Bruce R. Maxim and Quentin F. Stout (Bachelis1994). It was also mentioned in (Kitche1992),
but (Maxim1990) is listed as a reference.

No link to independent description publicly available. Please see details section for a synopsis.

### Similiar Exercises: 

Sorting: [OddEvenTranspositionSort]({{<ref "activities/oddeventranspositionsort">}}), [ParallelRadixSort]({{<ref "activities/parallelradixsort">}}), [CardSorting]({{<ref "activities/cardSorting">}}), [SortingNetwork]({{<ref "activities/sortingnetwork">}})

### Other activities by authors
(Bachelis1994): [ParallelAddition]({{<ref "activities/paralleladdition">}}), [FindSmallestCard]({{<ref "activities/findsmallestcard">}}), [SieveOfErastothenes]({{<ref "activities/sieveoferastothenes">}}), [OddEvenTranspositionSort]({{<ref "activities/oddeventranspositionsort">}}), [CardSorting]({{<ref "activities/cardSorting">}})


---

## Details

From (Bachelis1994): The goal of this exercise is to illustrate how sorting can occur in a stream/pipeline. The instructor feeds in numbers at one end of the pipeline, and the sorted output appears at the end.
The number of pipeline stages must equal the number of numbers to be sorted. Each student represents a separate pipeline stage, and receives cards from the right and passes them to the left. 

Students stand facing the classroom in a line. The instructor stands at the right-most end of the line and has the input numbers (which are written on large cards). The instructor is in charge of placing input into the pipeline and calling out the time steps. 

Students are given a set of instructions that read as follows:

```text
1. Receive number from your right. 
2. If you have two cards, pass the larger to your left during the next time step.
3. If, after you have started to receive cards from the right, you don't receive 
   a card from the right, pass one to the right whenever you have one to pass. 
``` 

The students follow the instructions every time step. The instructor calls out the time step with each iteration. To illustrate the sort, we consider a scenario with six numbers and six student processors. The instructor has the following six numbers written on separate index cards in order: 2, 6, 3, 7, 4, 1. The pipeline at the start is shown below (remember, students are facing the front of the class.)

```text
Step [Intr]          [Stu0] [Stu1] [Stu2] [Stu3] [Stu4] [Stu5]
0:   [1,4,7,3,6,2]          
1    [1,4,7,3,6]       2 
2:   [1,4,7,3]        (6,2)
3:   [1,4,7]          (3,2)  6
4:   [1,4]            (7,2) (3,6)
5:   [1]              (4,2) (7,3)   6
6:   []               (1,2) (4,3)  (7,6)
7:   []                1    (2,3)  (4,6)   7
8:   [1]                     2     (3,4)  (6,7)
10:  [1]               2            3     (4,6)   7
11:  [1,2]                   3             4     (6,7)
12:  [1,2]             3            4             6       7  
13:  [1,2,3]                 4             6              7  
13:  [1,2,3]           4            6             7         
14:  [1,2,3,4]               6             7       
15:  [1,2,3,4]         6            7
16:  [1,2,3,4,6]             7
17:  [1,2,3,4,6]       7
18:  [1,2,3,4,6,7]
```

### Variation (Kitchen1994)
(Kitchen1994) has a modified set of instructions from (Bachelis1994), where the output appears on the other side of the pipeline (instead of being returned back to the instructor). The numbers appear sorted 
(in ascending order) out of the stream. 

```text
1. Receive number from your right. 
2. If you have two cards, pass the smaller to your left during the next time step.
3. If, after starting to receive cards from the right, you don't receive 
   a card from the right (and you have one card), pass your number to the left 
   during the next time step. 
``` 

Here is how the pipeline operates using the description from (Kitchen1994):

```textStep 
[Intr]               [Stu0] [Stu1] [Stu2] [Stu3] [Stu4] [Stu5]   [Output]
0:   [1,4,7,3,6,2]          
1    [1,4,7,3,6]       2 
2:   [1,4,7,3]        (6,2)
3:   [1,4,7]          (3,6)  2
4:   [1,4]            (7,6) (3,2)
5:   [1]              (4,7) (6,3)   2
6:   []               (1,7) (4,6)  (3,2)
7:   []                7    (1,6)  (4,3)   2
8:   []                     (7,6)  (1,4)  (3,2)
9:   []                        7   (6,4)  (1,3)    2
10:  []                            (7,6)  (4,3)   (1,2)
11:  []                               7   (6,4)   (3,2)  1  
12:  []                                   (7,6)   (4,3) (2,1)   
13:  []                                      7    (6,4) (3,2)     [1]
14:  []                                           (7,6) (4,3)     [2,1]                 
15:  []                                              7  (6,4)     [3,2,1] 
16:  []                                                 (7,6)     [4,3,2,1] 
17:  []                                                    7      [6,4,3,2,1]
18:  []                                                           [7,6,4,3,2,1]  
```


(Kitche1994) recommends pointing out to the students that the algorithm does not automatically adapt to the problem size, and that when the set of numbers exceeds the number of pipeline stages, the 
algorithm breaks down. They recommend that students act this out (i.e., remove one pipeline stage and use the same set of numbers) if they have trouble visualizing why this is the case.


---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Algorithms, Analysis and Programming

**Elective**:
9\. Give examples of problems where pipelining would be an effective means of parallelization. [Familiarity]

---

## TCPP Topics Coverage

N/A

---

## Recommended Courses

* **K-12**: (Bachelis1994) recommends introducing concepts to students in a secondary-school mathematics or computer science class.

---

## Accessibility

This activity is generally accessible. For classrooms that contain blind students, we recommended that the cards being passed have Braille on them, so that the blind students 
can participate equally. 

---


## Assessment 

Unknown.

---

## Citations


* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel algorithms in undergraduate computer science courses (tutorial session)", in _Proceedings of the Twenty-first SIGCSE Technical Symposium 
  on Computer Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. Available: http://doi.acm.org/10.1145/323410.323415

* A. T. Kitchen, N. C. Schaller, and P. T. Tymann, "Game playing as a technique for teaching parallel computing concepts", _SIGCSE Bulletin_, vol. 24, no. 3, pp. 35–38, Sept. 1992.
  Available: http://doi.acm.org/10.1145/142040.142064

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing algorithms to life: Cooperative computing activities using students as processors", _School Science and Mathematics_,
  vol. 94, no. 4, pp. 176–186, 1994.