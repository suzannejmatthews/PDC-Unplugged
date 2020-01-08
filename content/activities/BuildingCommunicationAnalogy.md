---
title: "BuildingCommunicationAnalogy"
date: 2020-01-08T14:38:16-05:00
tcpp: ["TCPP_Algorithms"]
tcppdetails: ["CA_Communication"]
courses: ["CS1"]
senses: ["accessible"]
medium: ["analogy"]
---

## Original Author/link

Originally described Steven Bogaerts. 

No link to independent description. See Details section for more details.

---

## Details

This analogy is used to describe different types of inter-process communication. The scenario is as follows: suppose that you and a friend are trying to count the number of people in a building. How can this be accomplished?
Here are three different things you may say to your friend (from Bogaerts2014):

* _"I've counted the people in the basement (there are 27). Please go to the other floors and determine the total."_ This scenario corresponds to passing data at process creation.

* _"I'll count the basement, you count the other floors. Whenever you finish a floor, send me a text message with the number. I'll compute the final total."_ This scenario is used to illustrate message passing.

* _"I'll count the basement, you count the other floors. Let's jointly compute the total using a shared Google Doc. Whenever you finish a floor, update the value with the new total in the shared Google Doc. I will do the same when I finish the basement"._  This scenario illustrates shared memory.

---

## CS2013 Knowledge Unit Coverage

N/A

---

## TCPP Topics Coverage

### TCPP Algorithms

* Comprehend/Apply Communication: Understand --- via hands-on experience --- that inter-processor communication is one of the most challenging aspects of PDC.

---

## Recommended Courses

* **CS1**: Bogaerts introduced his concepts in a CS1 course.

---

## Accessibility

Generally accessible.

---


## Assessment 

(Bogaerts2014) used the building analogy to describe interprocess communication as part of a larger unit in parallelism in a CS1 course. He mentions that the total amount 
of time spent on parallelism was larger in the section that used analogies and hands-on activities compared 
to the one that presented the topics in a traditional lecture-style format (4 hours vs 90 minutes). However, 
the section that used analogies and hands-on activities performed better than those who received the 
information in a traditional lecture-format. Bogaerts argues that it is much better to spend more time on 
fewer parallel concepts in a hands-on way in an introductory course, rather than covering a variety of 
parallel concepts in a non-hands-on way. The final conclusion drawn is that analogies and hands-on activities 
enabled students to learn better and stimulated greater interest in the subject than a course that 
delivered the material in a typical lecture-style fashion. (Bogaerts2017) extends the assessment of the 
original paper, but found that while student interest increased, the desire to learn more decreased. The authors
theorize that this is because most of the students in the course were non-majors who will not be pursuing 
computing in the future. 

---

## Citations

* S. Bogaerts. "Limited Time and Experience: Parallelism in CS1". In _Proceedings of the 2014 IEEE 28th International Parallel & Distributed Processing Symposium Workshops  (IPDPSW'14)_, pp. 1071-1078. 2014.

* S. Bogaerts. "One step at a time: Parallelism in an introductory programming course". _Journal of Parallel and Distributed Computing_ Vol. 105, pp. 4-17. 2017.