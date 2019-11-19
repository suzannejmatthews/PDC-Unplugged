---
title: "FaultTolerantTokenRing"
date: 2019-11-14T12:37:23-05:00
cs2013: ["PD_CommunicationAndCoordination"]
courses: ["K-12", "Systems"]
tcpp: ["TCPP_Algorithms", "TCPP_CrossCutting"]
senses: ["visual", "auditory"]

draft: true
---

## Original Author/link

Originally described by Paolo A.G. Sivilotti and Murat Demirbas (Sivilotti2003) to 
illustrate Dijkstra's stabalizing token ring algorithm.

[Paper](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/sigcse_paper.pdf) and [materials](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/) available online:

* Middle School Slides (includes other activities) [PPT](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/fesc.ppt)
* High School Slides [PPT](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/starturn.ppt)
* 1 Page Synopsis [PDF](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/fault_tol.pdf)
* Token ring algorithm handout [PDF](http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/state.pdf)

---

## CS2013 Knowledge Unit Coverage

### Communication and Coordination

1. Use mutual exclusion to avoid a given race condition. [Usage]

---

## TCPP Topics Coverage

### Algorithms Topics 
*  Comprehend/Apply Communication: Understand --- via hands-on experience --- 
   that inter-processor communication is one of the most challenging aspects 
   of PDC. 

### Cross Cutting and Advanced Topics

* Know Fault tolerance: Large-scale parallel/distributed hardware/software 
  systems are prone to components failing but system as a whole needs to work.


---

## Recommended Courses

* **K-12**: (Sivilotti2003) successfully introduced the activity to 
  middle school girls in a 45-minute format. He later introduced the 
  same activity to high school students. 

* **Systems**: TCPP recommends discussing fault tolerance in systems courses.

* (Sivilotti2010) that concepts of self-stabalizing mutual exclusion can be 
  introduced to senior undergraduate students or graduate students.

---

## Accessibility

To make the activity accessible to blind students, it is recommended that
Braille cards representing 0 and 1 are used. The auditory component of the 
one-bar xylophone may be inappropriate for students who are hearing impaired.

---


## Assessment 

(Sivilotti2003) reported the activity could be completed in a 45 minute
period. Students were asked a number of questions, including rating the
exercises. On a scale from 1 (low) to 5 (high) students rated the fault tolerant
exercise as a 4.6, the highest of the three exercises. Students also made 
statements such as "I learned that computers have 'faults' that can be fixed" 
and "[i learned] how to make a program recover itself" (Sivilotti1999). 
Students were also asked to evaluate the overall quality of the computer 
science module on scale of 1 (low) to 5 (high), and rated the CS component 
of the workshop as 4.6. Note that this includes other activities.

(Sivilotti2003) also notes that the impact of musical element of the exercise 
"cannot be overstated", and that tones made it very obvious that when faults 
occurred. Students were gratified when the algorithm stabilized and a melody 
emerged.
 
---

## Citations

* P. A. G. Sivilotti, "Kinesthetic learning activities in an upper-division 
  computer science course", in *National Academy of Engineering Frontiers of 
  Engineering Education symposium*, 2010, poster; http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/nae-fee2010_poster.pdf

* P. A. G. Sivilotti and M. Demirbas, "Introducing middle school girls to
  fault tolerant computing", in *Proceedings of the 34th SIGCSE Technical
  Symposium on Computer Science Education (SIGCSE ’03)*. New York, NY, USA:
  ACM, 2003, pp. 327–331, [Online]: http://web.cse.ohio-state.edu/~sivilotti.1/outreach/FESC02/
  Available: http://doi.acm.org/10.1145/611892.611999

