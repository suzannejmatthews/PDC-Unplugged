---
title: "MessagePassingAcrobats"
date: 2020-01-08T16:20:50-05:00
tcpp: ["TCPP_Programming"]
tcppdetails: ["C_DistributedMemory"]
courses: ["DSA", "Systems", "oo_course"]
senses: ["movement"]
medium: ["roleplaying"]

---

## Original Author/link

Originally described by Steven K. Andrianoff and David B. Levine

No link to independent description available. See "Details" for more details.

---

## Details

The instructor plays the role of the main program, and students play the role of one or more acrobats. 

* The instructor chooses a few student volunteers to be "acrobats". It is very important that the instructor knows the names of the students (and that they have different names).

* Each acrobat is given the following script (from Andrianoff and Levine):

	```text
	You are an Acrobat

	When you are asked to Clap, you will be given a number. Clap your hands that many times.

	When you are asked KneeBend, you will be given a number. Stand up and sit down that many times. So, if you are given the number 2, you should stand up, sit down, stand up again, and sit down again.

	When you are asked to Count, reply verbally with the total number of exercises you have done. Note that KneeBend of 2 counts as 2 exercises, and Clap 3 counts as 3 exercises, etc.
	So, if you have done KneeBend twice and Clap three times (and nothing else), you should respond with "5"
	```

<p>

The instructor illustrates message passing by addressing student acrobats. For example, suppose that the students were John and Mary. The instructor would say things like "John Clap 3" or "Mary Knee Bend 4", or "John Count".

The activity reinforces the following concepts:

* Message passing protocols (naming an object, giving a request)
* parameter passing 
* return values (both void and non-void values are seen)


The authors mention that instructors should reference the activity frequently as the students learn more to help reinforce concepts.



---

## CS2013 Knowledge Unit Coverage

N/A

---

## TCPP Topics Coverage

### Programming Topics
* Comprehend Distributed Memory: Know basic notions of messaging among processes, different ways of message passing, collective operations

---

## Recommended Courses

* **Object Oriented Programming**: The authors use the activity in the context of an object oriented course and also a workshop. 
* **DSA/Systems**: TCPP recommends that distributed memory concepts be introduced in DSA or Systems.

---

## Accessibility

This activity may be difficult for students with mobility issues.

---


## Assessment 

Andrianoff and Levine used the activity on the first or second day of class in the context of a workshop or object oriented course. While the paper focuses mostly on object oriented design 
(that is the focus of the last two activities) the authors report that all the activities are generally beneficial.

---

## Citations

* S. K. Andrianoff and D. B. Levine. "Role playing in an object-oriented world". In _Proceedings of the 33rd SIGCSE technical symposium on Computer science education (SIGCSE'02)_. pp. 121–125. 2002. Available: https://doi.org/10.1145/563340.563386
