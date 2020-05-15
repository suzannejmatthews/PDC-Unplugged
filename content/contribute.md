---
title: "Contributing to PDC Unplugged"
---

### How to Contribute

Everyone is welcome to contribute to PDC Unplugged!  Please consider contributing if:

* If you have a great PDC unplugged activity that you created.
* If you know of a great PDC unplugged activity (be sure to provide links and/or citations).
* If you have assessed an existing listed unplugged activity.
* If you see typos or other need to correct an existing activity.

All submissions to PDC Unplugged are reviewed by the repository administrators. Once approved, the changes will 
appear almost immediately on the site.




### Activity Structure

Activities in the PDC Unplugged repository are created using MarkDown, a markup language that is simpler than HTML and in many ways resembles plaintext. To create a new activity, copy the following template to a textfile (for example `yourActivity.md`):

```
---
title: 
date: 
tags:
---

## Original Author/link


---

## CS2013 Knowledge Unit Coverage


---

## TCPP Topics Coverage


---

## Recommended Courses


---

## Accessibility


---


## Assessment 


---

## Citations

```

* **Original Author/link**: Please list the activity's author and any links to related external material. Paper citations and/or websites should be placed under the  "Citations" heading 

* **Details (optional)** The Details section is optional, but recommended if the activity is not publicly available on the web. Please include as much detail about the activity as you can. If you are getting information about an activity from an academic paper, it is important to cite the paper the activity is from and the original author. 

* **CS2013 Knowledge Unit Coverage** Next, please include the CS2013 knowledge units that match your activity. Please see the [CS2013 View]({{<ref "cs2013-overview">}}) page for a detailed listing of all PDC knowledge units. For each knowledge unit, please list the the title (e.g. `PD/Cloud Computing`) and the assoicated learning outcomes. The following code listing (extracted from [FindSmallestCard]({{<ref "activities/findsmallestcard">}})) illustrates how multiple knowledge units and learning outcomes associated for a particular activity can be listed:
	```text

---
## CS2013 Knowledge Unit Coverage

### PD/Parallel Decomposition

**Core Tier 1:**

2\. Identify opportunities to partition a serial program into independent 
        parallel modules. [Familiarity]

**Core Tier 2:**

4\. Parallelize an algorithm by applying task-based decomposition. [Usage]

### PD/Parallel Algorithms, Analysis & Programming - Core Tier 2

3\. Define "speed-up" and explain the notion of an algorithm's scalability in 
        this regard. [Familiarity]

4\. Identify independent tasks in a program that may be parallelized. [Usage]

6\. Implement a parallel divide-and-conquer (and/or graph algorithm) and 
        empirically measure its performance relative to its sequential analog.

---
	```

* **TCPP Topics Coverage** Please also include any relevant TCPP topics that match your activity. Please see the [TCPP View]({{<ref "tcpp-overview">}}) page for a detailed listing of all TCPP Topic Areas. The following code listing (extracted from [FindSmallestCard]({{<ref "activities/findsmallestcard">}})) illustrates how multiple topics associated with a particular activity can be listed:
	```text

---
## TCPP Topics Coverage

### Programming Topics 

* Comprehend Performance Metrics (Speedup): Understand how to compute speedup, 
      and what it means

### Algorithms Topics

* Comprehend Time: Recognize time as a fundamental computational resource that 
      can be influenced by parallelism
* Comprehend Scaling: Recognize the use of parallelism either to solve a given 
      problem instance faster or to solve larger instance in the same time 
      (strong and weak scaling)
* Apply Dependencies: Observe how dependencies constrain the execution order of 
      "embarrassing parallelism" to more complex computational structures
* Comprehend Divide & conquer (parallel aspects): Observe, via tree-structured 
      examples such as mergesort . . . how the same structure that enables divide 
      and conquer (sequential) algorithms exposes opportunities for parallel 
      computation
* Know Selection: Observe algorithms for finding order statistics, notably min 
      and max. Understand that selection can always be accomplished by sorting but 
      that direct algorithms may be simpler.

---
	```

* **Recommended Courses** If you have any recommendation for courses, please list them below. If you are citing an unplugged activity that exists in the literature, please include any recommendations for courses from the paper. Finally, if your activities align with any TCPP Topic Areas, please include the 
set of recommended courses associated with that topic area. Courses associated with each Topic Area can be found on the [TCPP View]({{<ref "tcpp-overview">}}) page.

* **Accessibility**: If you have any experience or thoughts on how to teach the unplugged activity to disabled students, please include them in this section. If you anticipate that a particular activity would be challenging for a particular group, please also mention it here. For example, an activity that heavily involves vision may not be the best choice for blind students. Include that information in this section, along with any suggestions on how blind students may participate equally in the exercise. 

* **Assessment**: If there is any assessment on the activity, please provide it in this section. Educators who use a particular acitivity in their classroom are welcome to include any evidence (qualitative or quantitative) about their experiences. Any assessment gleaned from the literature should have appropriate citations.

* **Citations**: PDC Unplugged  asks that all contributions cite the originating literature. If you are contributing an activity that was previously described, please cite the original set of authors, and provide a FULL citation to the paper, including any DOI information as available. If the PDF is available on-line, please link directly to it.  The following code listing (extracted from [FindSmallestCard]({{<ref "activities/findsmallestcard">}})) illustrates how journal and conference papers should be cited:

	```text

## Citations

* G. F. Bachelis, B. R. Maxim, D. A. James, and Q. F. Stout, "Bringing 
      algorithms to life: Cooperative computing activities using students as 
      processors", _School Science and Mathematics_, vol. 94, no. 4, pp. 176–186, 
      1994.

* B. R. Maxim, G. Bachelis, D. James, and Q. Stout, "Introducing parallel 
      algorithms in undergraduate computer science courses (tutorial session)", in 
      _Proceedings of the Twenty-first SIGCSE Technical Symposium on Computer 
      Science Education (SIGCSE'90)_. ACM, 1990, pp. 255. 
      Available: http://doi.acm.org/10.1145/323410.323415

	```


---

### Contributing Changes

**Note**: The paper associated with PDC Unplugged is currently in press. To submit changes or new activities to PDC Unplugged, please e-mail 
the administrator (suzanne DOT matthews AT westpoint DOT edu) with your markdown file or list of changes. 

All educators are free to e-mail the administrator (suzanne DOT matthews AT westpoint DOT edu) with their markdown file and/or list of changes. Those who are familiar with GitHub may choose to fork the repository, make their changes, and then [submit a pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork). This ensures that your contribution is acknowledged through GitHub. 


All activities are located under the `content/activities/` folder in the GitHub repository. To contribute to the repository, either modify the existing 
markdown file with your recommended changes or add a new markdown file to the folder. 

---


## Funding

<img src="../images/nsf.png" width="70" height="70" align="left"> This work is sponsored by National Science Foundation (NSF) Collaborative Research Grant DUE-1855761. _Collaborative Research: CSinParallel: Experiential Learning of Parallel and Distributed Computing through Sight, Sound, and Touch_. 

[logo]: ../images/nsf.png

