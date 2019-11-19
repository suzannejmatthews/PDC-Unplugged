---
title: "ByzantineGenerals"
date: 2019-11-13T14:02:06-05:00
cs2013: ["PD_CloudComputing"]
tcpp: ["TCPP_Programming", "TCPP_Algorithms", "TCPP_CrossCutting"]
courses: ["K-12", "CS1", "DSA", "Systems"]
senses: ["visual", "movement"]
draft: true
---

## Original Author/link

Originally described by William S. Lloyd (Lloyd1994)

No web-link to independent description available. See paper (Lloyd1994) 
for additional details.

---

## Details

Students learn of the classic Byzantine Generals problem by acting out 
scenarios.

The Byzantine Generals problem is a classic description of the consensus 
problem in distributed computing, where many independent processes must agree 
on a "true" value for a particular measurement (especially in the case where 
some processes become unreliable due to faults). Byzantine Fault Tolerance (BFT)
describes fault tolerance to "Byzantine" faults, where a rogue process may 
(instead of gracefully failing) continue to generate arbitrary data, making it 
difficult to detect as a faulty process. 

Today, the Byzantine General problem and BFT has its most well-known application 
in the creation of the Bitcon, where the Byzantine-tolerant blockchain enables 
the generation of a consensus of the system's state at any given time. 

Prior to the activity, students are familiarized with the conspiracies of 
the Byzantine Empire. (Lloyd1994) suggests telling the story of Empress Irene
of Athens, who ruled in stead of her underage son, Constantine VI from 780-790 AD. 
When Constatine assumed power, Irene was deposed and exiled. Through a 
conspiracy, Irene re-seized the throne in 797 AD, gouging out her son's eyes to 
prevent him from retaking the throne (he succumed to his wounds days later). 
Irene herself was overthrown by conspiracy in 802 AD.

### Introducing the Problem
The Byzantine generals problem is then introduced through the following 
scenario. It is midnight, and the Byzantine army is preparing to attack 
an enemy fort at dawn. The armed forces are split into several brigades, 
each led by its own general and occupying separate hills surrounding the fort. 
Each general must remain with his or her troops, and communicates with other 
generals by utilizing messengers that run from camp to camp. The generals 
must come to agreement on whether to attack at first light or retreat. The 
enemy's strength is such that unless a majority of the brigades attack, 
it will be a total rout and the Byzantine army will suffer a major defeat. The 
generals have agreed to abide by the vote of the majority, and will retreat 
if a majority decision cannot be reached.

While the army's lines of communication are secure (the messengers carry 
unforgeable messages stamped with the seal of the sender), there is a very 
real possibility that one or more of the Byzantine generals are traitors to the 
realm. For example, the traitors may trick a few of the loyal generals in 
attacking when the general consensus is to retreat, leading to a major 
military defeat. The problem is this: how can a loyal general ensure that 
his or her decision is the same as the majority of generals? What plan can 
be devised to ensure that the honest general will be joined by all loyal brigades
to attack?

### The Activity
The instructor should start by choosing three students to play generals, and 
have them stand in different corners of the classroom. A separate student is 
picked to act as a runner carrying messages between generals.

Ask the class:

* Why can't a general make a decision on a single message received from 
  the others? 

Consider the case where students A and B are loyal and C is a traitor. A 
wants to attack, and B wants to retreat. In a simple "majority vote" situation, 
all C needs to do is send an attack message to A to trick A into attacking, 
and a retreat message to B (or no message) to trick B into retreating. It may 
be helpful to write the messages received by each general on the board in 
separate columns (for example, A's column will read: A - Attack, B - retreat, 
C-attack, consensus - Attack). 

Next, the students are asked to consider the scenario where a fourth general 
(D) is added (pick a new student to play this part, and have them stand in a fourth 
corner of the room). Like general A, suppose general D also favors an attack. 

Ask the class:

* Suppose the new general D is loyal. Is it possible for general C to succeed 
  in his or her treachery? 

The answer is yes. All C needs to do is send A an attack message, and B and 
D to retreat. A will receive three attack messages (from A and D), and, having 
three of the four generals in agreement, prepare to attack. B and D however, 
will receive two votes for attack (from A and/or D) and two votes for retreat 
(from B and C). As a reminder, the decision is to retreat in the case of ties.
Therefore, come morning, general A will attack alone while B, C, and D retreat.

Next, ask the students:

* The majority method fails. What is the best way to foil the traitors plans?

With some guidance, students should come up with the solution that generals 
should circulate another round of messages, comparing notes to ensure that 
each general voted the same way in all messages. Thus, in the next round, all 
the generals send out the votes received by all the other generals.

Each loyal general determines the "true" vote of another general by seeing how 
the general voted to everyone else. So, A may write the following: 
(A): A - Attack, B - Retreat, C - Attack, D - Retreat; (B): A- Attack, B - 
Retreat, C - Retreat, D - Retreat; (<notextile>C</notextile>) A- Attack, B- Retreat C-(Attack or Retreat), D - Retreat; 
(D) A - Attack, B - Retreat, C - Retreat, D - Retreat.

Based on this, general A can see that generals B and D always indicates retreat,
while C either indicates attack (50%) of the time, or retreat (75%) of the time.
Therefore C's vote is recorded as retreat. General A can then note one attack 
vote (from A) and three retreat votes (from B, C, and D), and determine that 
it is best to retreat.

Next ask the students:

* Suppose there are _two_ traitors  (a conspiracy!), and that D is also a 
traitor just like C. Can general A still be tricked? Is there a way to foil 
the attack?

With two traitors, it is even easier to fool A into attacking, and B into 
retreating. A can be sent the messages from C and D saying to attack, while 
sending B messages to retreat. However, the exchanging of messages does 
not work this time. Consider the following scenario where C and D send 
A the message attack, and send B the message to retreat. A will therefore 
write the following:

(A): A - Attack, B - Retreat, C - Attack, D - Attack; (B): A- Attack, B - 
Retreat, C - Retreat, D - Retreat; (<notextile>C</notextile>) A- Attack, B- Retreat C-Attack, D - Attack; 
(D) A - Attack, B - Retreat, C - Attack, D - Attack.

From this set of messages, it will appear to A that C and D are indicating that 
they will attack (even though B correctly reports that C and D sent a message 
indicating that they are retreating). So, A will attack.

In contrast, B may write the following:

(A): A - Attack, B - Retreat, C - Attack, D - Attack; (B): A - Attack, B - Retreat, 
C - Retreat, D-Retreat. (<notextile>C</notextile>) A - Attack, B - Retreat, C - Retreat D - Retreat, 
(D) A - Attack, B - Retreat, C - Retreat, D-Retreat. 

In this case, B is fooled into thinking that C and D are in agreement of 
retreating, and will retreat. In the case of two traitors, it is impossible 
for them to be overcome.

Lastly, ask general D to sit down. Ask the class:

* What about the original scenario with three generals (A, B, and C) and only 
  one disloyal general. Can the traitor still be detected?

In the first round of messages, C can tell A to attack and B to retreat. In 
the second round however, C can forward seperate messages to A and B. 

A could then write the following:
(A): A - Attack, B - Retreat, C - Attack; (B): A - Attack, B - Retreat, 
C - Retreat; (<notextile>C</notextile>) A - Attack, B - Retreat, C - Attack. 

In this scenario, while B correctly reports that C told them to retreat, the 
majority decision for C is two attacks and one retreat. So, A will interpret 
C's decision as "attack", and will attack. 

Likewise, B can write the following:
(A): A - Attack, B - Retreat, C - Attack; (B): A - Attack, B - Retreat, 
C - Retreat; (<notextile>C</notextile>) A - Attack, B - Retreat, C - Retreat. 

In this case, while A correctly reports that C reported to attack, the majority 
of B's messages indicate that C indicates to retreat. Therefore, B will 
interpret C's decision as "retreat", and will retreat.

Conclude with the fact that in order for loyal generals to defeat traitors, 
there must be at least over three times as many loyal generals as traitors (i.e. 
3_t_ +1, where _t_ is the number of traitors). (Lloyd1994) also recommends 
telling students that while the above dramatization is useful for exploring 
the problem, formal proof methods are necessary to make the argument 
correctly to computer scientists.

### Relating it to Distributed Computing

Each general represents a process executing on a separate distributed 
processor. A traitor represents an unpredictably faulty processor. The entire 
army represents a distributed computer system in which separate elements 
cooperate to achieve a task. Prime questions for discussion include:

* The generals work _concurrently_ to make their decisions. When is _concurrency_ 
  useful in computing?

* The generals cooperate through they are in different camps. How to 
  processes executing on different processors form a distributed computing 
  system?

* Generals communicate through runners. How do distributed processes 
  communicate? What are the effects of interprocess communication on security?

* The Byzantine army can be effective even though some generals are traitors. 
  How can distributed systems increase reliability?

* Suppose instead that the enemy captures/corrupts a runner. What kinds of 
  failures can occur in distributed computing systems?

Lastly, the instructor can guide discussions on more advanced issues related 
to viruses, hacking, and encryption. For example, message passing amongst 
generals can be used to illustrate encryption techniques. Lastly, the 
instructor can relate the Byzantine General problem to the construction of the 
blockchain.


---

## CS2013 Knowledge Unit Coverage

### Cloud Computing (Elective)

2\. Explain strategies to synchronize a common view of shared data across a collection of devices. [Familiarity]

---

## TCPP Topics Coverage

### Programming Topics

* Comprehend Distributed Memory: Know basic notions of messaging among processes, different ways of message passing, collective operations.

### Algorithm Topics

* Comprehend/Apply Communication: Understand --- via hands-on experience --- that inter-processor communication is one of the most challenging aspects of PDC.

### Cross Cutting and Advanced Topics

*  Know Fault tolerance: Large-scale parallel/distributed hardware/software systems are prone to components failing but system as a whole needs to work. 
*  Know Cluster Computing: Be able to describe a cluster as a popular local-memory architecture with commodity compute nodes and a high-performance interconnection network. 
*  Know Consistency in Distributed Transactions: Recognize classic consistency problems. Know that consistency maintenance is a primary issue in transactions issued concurrently by multiple agents.
*  Know Security in Distributed Systems: Know that distributed systems are more vulnerable to privacy and security threats; distributed attacks modes; inherent tension between privacy and security.

---

## Recommended Courses

* **K-12/CS1**: Author reports exploring the Byzantine Generals problem in 
  CS1 at West Georgia College, and with 9-12th greaters in a mathematics 
  enrichment program (Lloyd1994). In addition TCPP recommends that the topic 
  of consistency in distributed systems can be introduced as early as CS1.

* **DSA/Systems** - TCPP recommends that distributed systems topics such as message 
   passing can be covered in DSA or systems courses.In addition, issues such as 
   fault tolerance, consistency and security are appropriate for Systems courses.

---

## Accessibility

Blind students may have issues with this activity (playing the role of generals, 
unless Braille (attack/retreat) cards are provided in advance for them to receive. 

We don't anticipate this study to be difficult for mobility impaired students, 
since they can sit in a corner of the classroom.

---


## Assessment 

While formal assessment is not provided, the author reports that they "have 
found it to be one of the most popular topics covered" in the high school and 
CS1 environments (Lloyd1994).


---

## Citations

* W. S. Lloyd, "Exploring the byzantine generals problem with beginning 
  computer science students", SIGCSE Bull., vol. 26, no. 4, pp. 21–24, 
  Dec. 1994. Available: http://doi.acm.org/10.1145/190650.190656
