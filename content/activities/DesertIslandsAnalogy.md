---
title: "DesertIslandsAnalogy"
date: 2019-11-05T15:34:13-05:00
cs2013: ["PD_ParallelDecomposition", "PD_ParallelArchitecture", "PD_ParallelPerformance"]
cs2013details: ["PD_5", "Arch_1", "Arch_3", "Arch_4", "Arch_5", "Arch_8", "Perf_3"]
tcpp: ["TCPP_Architecture", "TCPP_Programming"]
tcppdetails: ["C_Taxonomy", "K_Heterogeneous", "K_Hybrid"]
courses: ["CS2", "DSA", "Systems"]
senses: ["analogy", "visual", "movement"]
draft: true
---

## Original Author/link

Oklahoma Supercomputing Center for Educaton and Research
([OSCER](http://www.oscer.ou.edu/education.php))

"Supercomputing in Plain English" - "Distributed Multiprocessing", Slides 19-25.

* Available in: [PPT](http://www.oscer.ou.edu/Workshops/DistributedParallelism/sipe_distribmem_20180306.pptx) and [PDF](http://www.oscer.ou.edu/Workshops/DistributedParallelism/sipe_distribmem_20180306.pdf)
* Also described in (Neeman2006)

The following questions from (Neeman2006) can be used to stimulate discussion:

* Suppose that each student is on his or her own island far away from everyone 
  else. Are any of them aware of anyone else? Do they know who is at the 
  other end of the phone line? 
* Next, read out the set of instructions from a piece of paper. Ask the people who had that set of instructions to raise their hands. Everyone should raise their hands. Assuming that everyone is on a separate island, is it possible for anyone to be aware of the work that anyone else is doing (or if it is the same program?)

The point is that someone very clever (the instructor) can plan it out ahead of 
time that everyone is running the same program on different units of data. 
Together therefore, they can solve a problem much larger (and faster) than any 
single person can solve.

---

## Variations

**Activity**:
It is possible to act this out.
 
* Students physically sitting at separate desks represent CPUs.
  Each person has a basket in front of their desk, representing their voice
  mailbox. Each basket is denoted a phone number.
* The instructor should hand each person at a desk a piece of paper with some  
  pre-printed instructions, and different colors of paper (representing data). 
* Instead of making phone calls, they can write answers on the color paper,  
  crumple it up and toss the result into the appropriate baskets of other nodes.
* It is important for students to be able to see that each volunteer is working 
  at their own pace and independently, in isolation of everyone else. 
* Use the questions above to stimulate discussion about the activity.

**GPUs:**
The analogy can also be extended to describe processes on GPUs. To act out 
this analaogy, have a collection of chairs organized in a row (no desks), 
to represent an "archipelago" of smaller islands. Have a person sit in each 
chair. Each person in a chair represents a GPU core. 
Next to the row of chairs is a person at a desk (representing the much larger CPU).

* Since chairs are smaller than desks, the types of work the GPU cores can 
  accomplish is very little. Suppose it's just simple math. 
* The same set of instructions are sent to all the GPU cores simultaneously 
  from the CPU (i.e. X+Y-Z), along with different data (numbers). 
* As soon as the machines finish receiving their instructions, they perform 
  each calculation in lock-step fashion. 
* At the end, each machine simultaneously sends the result back to the CPU.
* The CPU (human) then takes care of the more complicated work, including 
  communicating the final result back to the user.

This can conclude with a discussion of Flynn's taxonomy, where we talk about 
MIMD (distributed, multicore) architectures, and SIMD (GPU) architectures.

---

## CS2013 Knowledge Unit Coverage

### Parallel Decomposition (Core Tier 2)

5\. Parallelize an algorithm by applying data-parallel decomposition. [Usage]

### Parallel Architecture (Core Tier 1, Core Tier 2, Elective)

1\. **Core Tier 1**: Explain the differences between shared and distributed memory. [Familiarity]

3\. **Core Tier 2**: Characterize the kinds of tasks that are a natural match for SIMD machines. [Familiarity]

4\. **Elective**: Describe the advantages and limitations of GPUs vs. CPUs. Familiarity]

5\. **Elective**: Explain the features of each classification in Flynn's taxonomy. [Familiarity]

8\. **Elective**: Describe the key performance challenges in different memory and distributed system topologies. [Familiarity]


### Parallel Performance (Elective)

3\. Describe how data distribution/layout can affect an algorithm's communication costs. [Familiarity]

---

## TCPP Topics Coverage

### Architecture Topics

* Comprehend Parallel Taxonomy: Flynn's taxonomy, data vs. control parallelism, shared/distributed memory.
* Know Heterogeneous (e.g., Cell,on-chip GPU): Recognize that multicore may not all be the same kind of core.



### Programming Topics

* Comprehend SPMD: Understand how SPMD program is written and how it executes.
* Comprehend Distributed Memory: Know basic notions of messaging among processes, different ways of message passing, collective operations.
* Know Hybrid: Know the notion of programming over multiple classes of machines simultaneously (CPU, GPU, etc.)
---

## Recommended Courses
* Authors present the analogy to attendees of their "Supercomputing in Plain 
  English" workshop series. According to (Neeman2008), the concepts have been 
  presented to students as young as elementary school to adult attendees. 
* **CS2/DSA/Systems**: TCPP recommends that the SPMD concept be covered in 
  CS2 or DSA, and that architecture topics be covered in *Systems*. 


---

## Accessibility

* Students with mobility issues may have issues with the activity version of 
  this exercise (throwing). 
* Blind students will likely have issues with this exercise.

---


## Assessment 

Unknown. (Neeman2006) describes the different analogies. There is no assessment 
provided in (Neeman2006) or (Neeman2008).


---

## Citations

* OSCER. "Distributed Multiprocessing". *Supercomputing in 
  Plain English: A High Performance Computing Workshop Series*. Online, 
  last accessed 5 November 2019. http://www.oscer.ou.edu/Workshops/DistributedParallelism/sipe_distribmem_20180306.pdf

* H. Neeman, L. Lee, J. Mullen, and G. Newman, "Analogies for teaching parallel 
computing to inexperienced programmers", in *Working Group Reports on ITiCSE 
on Innovation and Technology in Computer Science Education*, ser. ITiCSE-WGR'06. 
New York, NY, USA: ACM, 2006, pp. 64–67. Available: http://doi.acm.org/10.1145/1189215.1189172

* H. Neeman, H. Severini, and D. Wu, "Supercomputing in plain english: Teaching
cyberinfrastructure to computing novices" *SIGCSE Bull.*, vol. 40, no. 2,
 pp. 27–30, June 2008. Available: http://doi.acm.org/10.1145/1383602.1383628

