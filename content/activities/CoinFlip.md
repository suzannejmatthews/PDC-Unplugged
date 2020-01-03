---
title: "CoinFlip"
date: 2019-12-11T15:00:06-05:00
cs2013: ["PD_ParallelArchitecture"]
cs2013details: ["Arch_3", "Arch_4"]
tcpp: ["TCPP_Architecture"]
tcppdetails: ["K_SIMDVector", "K_MIMD"]
courses: ["systems"]
senses: ["touch", "visual"]
medium: ["coins"]

---

## Original Author/link

Originally described by Andrew Kitchen, Nan Schaller and Paul Tyman (Kitchen1992).

No link to independent description available. See Details for a synopsis.

---

## Details
The goal of this activity is to help students visualize the difference between execution on a SIMD architecture vs a MIMD architecture. Each student plays a processor and is given a coin. 

They are presented with the following algorithm:

```text
1. flip coin.
2. check if heads.
2. If so, raise hand.
```

The goal is to determine the total number of heads over all the coin flips.

### Illustrating MIMD

When the instructor says "go", each executes the algorithm and raises their hand if they receive heads. The instructor counts the number of raised hands to determine the final result.  It should be emphasized to students watching the exercise that each student acts independently and executes the algorithm at their own pace. 


### Illustrating SIMD

The instructor reads the instructions out loud step by step. As the instructor reads each instruction, the student processors perform the instruction in lock step fashion. Students can only perform their instruction when the instructor reads it aloud. Thus,

* When the instructor says "flip coin", all the students flip coins.
* When the instructor says "check if heads", all the students look down to see if they got heads on their coin flip.
* When the instructor says "raise hand if heads", all the students who got heads raise their hands.

At the end, the instructor counts off the number of raised hands to determine the number of heads. This exercise emphasizes to students that SIMD instructions are executed in lock-step fashion, in comparison 
to MIMD, where each thread has more autonomy to execute their instructions.


---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Architecture

**Core Tier 2**

3\. Characterize the kinds of tasks that are a natural match for SIMD machines.

**Elective**:
4\. Describe the advantages and limitations of GPUs vs. CPUs.

---

## TCPP Topics Coverage

### Architecture Topics

* Know SIMD/Vector (e.g., SSE, Cray): Describe uses of SIMD/Vector (same operation on multiple data items) 
* Know MIMD: Identify MIMD instances in practice (multicore, cluster, etc.)

---

## Recommended Courses

* **Systems**: TCPP recommends that architecture topics be covered in a systems course.

---

## Accessibility

This activity may be difficult for students who are visually impaired. To enable those students to participate in the exercise, we suggest giving students a larger coin or tile (say a dominos tile or mahjong tile), where the difference between the two sides can be clearly distinguished. 

---


## Assessment 

In  (Kitchen1992), it is mentioned that a component of this exercise was used at an NSF Undergraduate Faculty Enhancement workshop at Colgate University in the Summer of 1991. A panelist at SuperComputing'91 also mentioned that the SIMD component of this exercise was used successfully in an introductory parallel computing course at Bucknell University. No formal assessment mentioned.

---

## Citations

* A. T. Kitchen, N. C. Schaller, and P. T. Tymann, "Game playing as a technique for teaching parallel computing concepts", _SIGCSE Bulletin_, vol. 24, no. 3, pp. 35–38, Sept. 1992.
  Available: http://doi.acm.org/10.1145/142040.142064