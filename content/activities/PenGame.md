---
title: "PenGame"
date: 2019-11-05T14:30:34-05:00
cs2013: ["PD_CommunicationAndCoordination"]
cs2013details: ["CAC_2"]
tcpp: ["TCPP_Programming"]
tcppdetails: ["K_DataRaces"]
courses: ["K_12", "CS0", "DSA", "Systems"]
senses: ["visual"]

---

## Original Author/link

Oklahoma Supercomputing Center for Educaton and Research 
([OSCER](http://www.oscer.ou.edu/education.php))

"Supercomputing in Plain English" - Shared Memory, Slides 103-104.

* Available in: [PPT](http://www.oscer.ou.edu/Workshops/SharedMemoryParallelism/sipe_sharedmem_20180227.pptx) and [PDF](http://www.oscer.ou.edu/Workshops/SharedMemoryParallelism/sipe_sharedmem_20180227.pdf)
* Also described in (Neeman2006)

After the first game (Take the Pen), students are asked 
"Can the outcome be predicted in advance?" They are led to the answer "no", 
and to understand this is situation represents a race condition (Neeman2006). 

The question is repeated after the second game (Look at the Pen). Here, 
students are led to the answer "yes". Through the game, they come to 
understand that race conditions occur on writes (taking the pen) rather 
than reads (looking at the pen). (Neeman2006).

---

## CS2013 Knowledge Unit Coverage

### Communication and Coordination

2\. Give an example of an ordering of accesses among concurrent activities 
    (e.g., program with a data race) that is not sequentially consistent. 
    [Familiarity]	

---

## TCPP Topics Coverage

### Programming Topics

* Know Data Races: Know what a data race is, and how 
to use synchronization to prevent it.

---

## Recommended Courses

* Authors present the analogy to attendees of their "Supercomputing in Plain 
  English" workshop series. According to (Neeman2008), the concepts have been 
  presented to students as young as elementary school to adult attendees. 
* **K-12/CS0** - The Pen Game is an easy way to present the notion of a race 
  condition to K-12 students and non-majors (CS0).
* **DSA/Systems** - TCPP recommends that the notions of race condtions and 
  data races may be most appropriately covered in a DSA or Systems course.

---

## Accessibility

This game may be difficult for blind students. For students who are deaf, 
instead of saying the word "go", the instructor could offer a visual cue 
(e.g. thumbs up) instead. 

---


## Assessment 

Unknown. (Neeman2006) describes the different analogies. There is no assessment 
provided in (Neeman2006) or (Neeman2008).

---

## Citations

* OSCER. "Shared Memory Multithreading". *Supercomputing in 
  Plain English: A High Performance Computing Workshop Series*. Online, 
  last accessed 5 November 2019. http://www.oscer.ou.edu/Workshops/SharedMemoryParallelism/sipe_sharedmem_20180227.pdf

* H. Neeman, L. Lee, J. Mullen, and G. Newman, "Analogies for teaching parallel 
computing to inexperienced programmers", in *Working Group Reports on ITiCSE 
on Innovation and Technology in Computer Science Education*, ser. ITiCSE-WGR'06. 
New York, NY, USA: ACM, 2006, pp. 64–67. Available: http://doi.acm.org/10.1145/1189215.1189172

* H. Neeman, H. Severini, and D. Wu, "Supercomputing in plain english: Teaching
cyberinfrastructure to computing novices" *SIGCSE Bull.*, vol. 40, no. 2,
 pp. 27–30, June 2008. Available: http://doi.acm.org/10.1145/1383602.1383628

