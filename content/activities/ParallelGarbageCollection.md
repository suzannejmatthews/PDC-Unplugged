---
title: "ParallelGarbageCollection"
date: 2020-01-06T14:36:44-05:00
cs2013: ["PD_CommunicationAndCoordination"]
cs2013details: ["CAC_8"]
tcpp: ["TCPP_Algorithms"]
tcppdetails: ["K_Asynchrony", "C_GraphSearchAlgorithms"]
courses: ["CS2", "DSA", "ParProg","Graduate"]
senses: ["movement", "visual"]
medium: ["roleplaying", "cards"]
---

## Original Author/link

Originally described by Paulo A.G. Sivilotti and Scott Pike

[Paper](http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/sigcse07.pdf) and [poster](http://web.cse.ohio-state.edu/~sivilotti.1/research/publications/nae-fee2010_poster.pdf) available online:

---

## Details

See paper for details. In summary, this activity presents a directed graph with a distinguished vertex (labeled the root). Vertices are connected to each other with some number of edges.
The end-goal is determine the set of reachable vertices from the root ("food") and distinguish them from the set of non-reachable vertices ("garbage"). Complicating the process is the 
presence of a mutator process that can modify (add or delete) edges; the set of vertices stay constant. 

A group of 15 to 20 students are chosen for the activity to represent the vertices of the graph. Each student is given a hat and a set of 12 index cards. One student play the part of the root.

* The activity starts with each student writing their names on all their index cards. Students should give the activity leader three cards, and place the rest in their pocket.
* The activity leader shuffles the set of collected cards and redistributes them to the set of student vertices. Each student vertex holds the cards they receive in their hands. These received cards represent _edges_ from the 
  student holding the card to the students whose name is written on the held cards.
* Graph mutation occurs amongst the student vertices themselves:
      * deleting an edge: to delete an edge, student simply discard one or more of the cards they hold in their hand.
      * adding an edge: to add an edge, the student must add a vertex that is connectable from the root. To do so, they must look at the set of index cards held by the root, visit a person whose name is written on that card, look at 
        that person's index cards, visit a person on one of those index cards, and so forth, until the student goes the desired number of hops. The student then takes a card from the destination vertex's reserves.
* One additional student volunteer plays the role of the marker, and executes the "naive" marking algorithm. In other words, the marker starts at the root, placing a hat on the root's head. The marker then travels to all reachable vertices from the root and places hats on each reachable vertex's head. The end goal is to have all the "food" (reachable) vertices wearing hats, while all the "garbage" (unreachable) vertices do not have hats.
* When the marker determines that s/he has completed their task, everyone goes and sits down (no more mutations occur). The work can be checked via a depth first search. The root first stands up, and reads off the name of an individual on one of the index cards they are holding. That person then stands up and reads off a name of one of their index cards. This process continues until everyone who is standing has read off all the names on their index cards. The people who are standing are the reachable vertices, while the people sitting down are the unreachable vertices. If there is anyone who is sitting down who is wearing a hat (or vice versa), the algorithm has failed.


This activity is effective at demonstrating an _incorrect_ algorithm. To force an incorrect execution case, the instructor joins the activity as a special node:

*  Ahead of time, two student vertices are marked as "special", and have edges to the instructor (e.g. cards with instructor's name on it). No one else has an edge to the instructor, and the two special student vertices _always_ are 
   accessible from the root in this activity (i.e., the root never deletes its edges to the special vertices). 
*  During the activity, the special vertices hold their instructor edge card in their hand. If the marker process comes around to check them, they casually drop that edge to the ground (e.g. delete the edge). Once the marker process 
   moves on, they pick the instructor edge back up off the floor. In this manner, the marker process never reaches/marks the instructor node.
 

**Tips from the authors**
* Ensure that students know each other's names prior to the activity. 

* No-one (save for the instructor, two special students and root student) should know about the instructor being part of the activity and the special arrangement with the instructor's edge cards. To help, the two special vertices should be far apart from each other. 

* To ensure that the are students who are unreachable vertices, consider splitting the student vertices into two groups. Student in each group should only receive edge cards from other group members. Next, the students in the group that does not contain the root should get some edge cards of the people in the group that contains the root (i.e. the other group contain edges pointing toward the group with the root).

---

## CS2013 Knowledge Unit Coverage

### PD/Communication and Coordination

8\. Write a test program that can reveal a concurrent programming error; for example, missing an update when two activities both try to increment a variable. 

---

## TCPP Topics Coverage

### Algorithms Topics

* Know Asynchrony: Understand asynchrony as exhibited on a distributed platform, its strengths (no need for synchs) and pitfalls (the danger of race conditions)
* Comprehend Graph Search Algorithms: Know how to carry out BFS- and DFS-like parallel search in a graph or solution space (1 hour)

---

## Recommended Courses

The instructors used this activity in an upper-level undergraduate course on parallel programming. They also recommend the activity for graduate students.

* **CS2**: TCPP recommends that asynchronous communication can be introduced as early as CS2.
* **DSA**: TCPP recommends that parallel graph search algorithms be covered in DSA.

---

## Accessibility

The activity may be difficult for students who are blind and/or have mobility issues.


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