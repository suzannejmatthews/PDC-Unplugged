---
title: "ConcertTickets"
date: 2019-12-06T17:54:13-05:00
cs2013: ["PD_ParallelDecomposition", "PD_CommunicationAndCoordination", "PD_CloudComputing"]
cs2013details: ["PD_1", "CAC_2", "CAC_5", "CAC_7", "CAC_8", "CC_2"]
tcpp: ["TCPP_Programming", "TCPP_CrossCutting"]
courses: ["CS1"]
senses: ["analogy"]
draft: true
---

## Original Author/link

Originally described by Yifat Ben-David Kolikant (Kolinkat2001). Modified for a 
CS1 audience by Gary Lewandowski, Dennis Bouvier, Robert McCartney, Kate Sanders, and Beth Simon in 2007 (Lewandowski2007, Lewandowski2010)

No on-line resources available. See details for description.

---

## Details

### CS1 Use-Case
The following scenario is presented to students entering CS1 on their first 
day (Lewandowski2010):

> Suppose a Ticket Sale Company sells concert tickets in the following way:
> When a customer calls and asks for a _n_ seats, the seller (1) finds the _n_ 
> best avaiable seats; (2) marks those _n_ seats as unavailable; and  (3) deals with customer payment options and either e-mails ticket receipt 
> or sends tickets to the Will Call Box Office (lets customer pick up tickets 
> day of show). Now suppose there are two sellers working at the same time. 
> What problems could arise, and how can we avoid them?

Students should be allowed to answer in whatever long-form way they choose.
This could be done electronically (through a text-box) or written down and 
submitted. 

If done in class, the authors suggest that instructors choose a subset of 
student-generated solutions for further discussion. For example, 

* What is the key problem? (a seat gets accidentally sold to multiple people). 
  This is called a "race condition".

* Even in "fast" systems (blazingly fast sellers), it is possible to have 
  race conditions. It should be emphasized to students that race conditions 
  can occur despite speed.

* Instructors can use responses that "pass the buck" (vendors can mark a seat 
  as unavailable and sell it instaneously). For these responses, let students 
  know that there can be delay that could occur between the time seats are 
  marked as unavailable and when they are sold. This is a good starting 
  point on a discussion of atomic operations. 

* Also ask students what would happen if a credit card payment did not go 
  through, or if the customer changes their mind (i.e. what if marking a seat 
  as reserved and purchasing it was not atomic)?

* Instructors should use centralized solutions (sellers pass the 
  responsibility of making seat assignments to some centralized resource like 
  a database or where each seller had their own private set of seats that only 
  they sell) to discuss interleving instructions (e.g. how will one seller know 
  that another seller has reserved the seats?) or serializing the process. 

* Instructors should use solutions that do not scale well to discuss scaling 
  issues (e.g. only one vendor on a cell-phone is allowed in the concert hall 
  at any given time; at that point they get the "best" seats for their 
  customer, marks them as "taken" and leaves. The scaling issue arises as this 
  is not tenable for larger concert halls).  

* Instructors should stress the real-world applicability of this problem. 
  Ask the students where they have seen this in the real world. 

### Original Proposed by Kolikant

The original was provided as an assignment by (Kolikant2001) to her students 
on the first day of class in an upper-level concurrency course. The following 
is reproduced from (Lewandowski2007) as a summary of what was proposed by 
(Kolikant2001):

A ticket office sells movie tickets for a certain play. The next client always 
gets the best avaialable ticket (each client can only purchase one ticket).
The vendor runs computer software that determines what is the next best 
available seat, and prints the ticket for the client. This is equivalent to a 
buttom push.

The following procedures are defined in the software:

```c

// returns index of best available seat in hall
// returns -1 if no seats are available
int bestAvailableSeat(Array Hall); 

//marks seat noted by the index as being "taken". 
//once function completes, the seat is marked as being taken with customer's name.
void markAvailableSeat(int seat, string customer);

//prints a ticket associated with the index (has customer's name on it) 
void printTicket(int seat);
```

The software handles a client using the following set of steps:

```c

int seat = bestAvailableSeat(Hall);
if (seat != -1) {
    markAvailableSeat(seat);
    printTicket(seat);
}
```

The owners of the play decide to add another ticket office. Each ticket office 
open at the same time and sell tickets for the same play. Each office has its 
own printer for printing tickets. 

Develop a system according to the following steps:

1. What is the required hardware? (screens, printers, keyboards, etc.). Specify 
   how the hardware is distributed in the system.

2. Write pseudocode for the software of the required system (where tickets are 
   being sold in two offices for the same play). You may use the procedures 
   defined above.

---


## CS2013 Knowledge Unit Coverage

### PD/Parallel Decomposition Core Tier 1

1\. Explain why synchronization is necessary in a specific parallel program. [Usage]

### PD/Communication and Coordination 

**Core Tier 1**

2\. Give an example of an ordering of accesses among concurrent activities (e.g., program with a data race) that is not sequentially consistent. [Familiarity]


**Core Tier 2**

5\. Write a program that correctly terminates when all of a set of concurrent tasks have completed. [Usage]

7\. Explain why checks for preconditions, and actions based on these checks, must share the same unit of atomicity to be effective. [Familiarity]

8\. Write a test program that can reveal a concurrent programming error; for example, missing an update when two activities both try to increment a variable. [Usage]

### PD/Cloud Computing 

2\. Explain strategies to synchronize a common view of shared data across a collection of devices. [Familiarity]


---

## TCPP Topics Coverage

### Programming Topics

* Know Concurrency Defects (Data Races): Know what a data race is, and how to use synchronization to prevent it.

### Cross Cutting and Advanced Topics 

* Know Consistency in Distributed Transactions: Recognize classic consistency problems. Know that consistency maintenance is a primary issue in transactions issued concurrently by multiple agents.

---

## Recommended Courses

(Kolikant2001) presented the original exercise in an upper-level 
course on concurrency.

* **CS1**: (Lewandowski2007) taught the concepts in a CS1 course.
* **CS2/Systems**: TCPP recommends that consistency in distributed 
  transactions can be covered in CS2 and/or systems.
* **DSA**: In addition to systems, TCPP recommends that data races can be 
  covered in DSA.

---

## Accessibility

This assignment seems generally accessible. For students who are blind, the 
prompt needs to be made available in Braille or through a screen reader so that 
students can give their answers. 

---


## Assessment 

(Kolikant2001) presented the problem as the first assignment in an upper-level 
course on concurrency. Despite the differences in the solutions, Kolikant found 
that she could classify all the responses into five main categories, including 
three centralized solutions, and two decentralized solutions. Found that while 
many students proposed centralized solutions, most failed to recognize the 
race condition component. 

(Lewandowski2007, Lewandowski2010) created a simpler, less programming specific 
version which they presented to CS1 students as an open prompt. Students submitted 
long form english-sentence paragraph answers, rather than psuedo-code. Unlike 
(Kolikant2001), students in this populace submitted multiple solutions. 
(Lewandowski2010) reports that with the more open-ended responses, 71% of students 
came up with at least one "reasonable" response, and most students (97%) 
identified the main problem of interest (it may be possible to give a 
a particular seat to more than one person). Both studies support the notion 
of constructivism, which operates under the assumption that students learn by 
refining and extending their own existing knowledge. Both sets of researchers 
argue thatt "real-world" scenarios like the ticket system is preferable to 
clever stories (Dining Philosophers, Sleeping Barbers, etc.). 


---

## Citations

* G. Lewandowski, D. J. Bouvier, T.-Y. Chen, R. McCartney, K. Sanders, 
  B. Simon, and T. VanDeGrift, "Commonsense understanding of concurrency: 
  Computing students and concert tickets", _Communications of the ACM_, vol. 
  53(7), pp. 60–70, July 2010. Available: http://doi.acm.org/10.1145/1785414.1785438

* G. Lewandowski, D. J. Bouvier, R. McCartney, K. Sanders, and B. Simon, 
  "Commonsense computing (episode 3): Concurrency and concert tickets", in 
   _Proceedings of the Third International Workshop on Computing Education 
   Research (ICER'07)_. 2007, pp. 133–144. Available: http://doi.acm.org/10.1145/1288580.1288598

* Y. B.-D. Kolikant, "Gardeners and cinema tickets: High school students' 
  preconceptions of concurrency", _Computer Science Education_, 11(3), 
  pp. 221–245, 2001. Available: https://doi.org/10.1076/csed.11.3.221.3831
