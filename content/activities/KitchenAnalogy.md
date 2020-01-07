---
title: "KitchenAnalogy"
date: 2020-01-07T08:40:19-05:00
cs2013: ["PD_ParallelArchitecture", "PD_ParallelPerformance"]
cs2013details: ["Arch_7", "Perf_4", "Perf_6"]
tcpp: ["TCPP_Architecture", "TCPP_Programming"]
tcppdetails: ["C_CacheOrganization", "K_DataLayout", "K_DataLocality", "K_FalseSharing"]
courses: ["DSA", "ProgLang"]
senses: ["visual"]
medium: ["analogy"]
---

## Original Author/link

_The kitchen analogy is a fairly well-known analogy for discussing the memory hierarchy. I am not sure who first described it. If someone knows, please contact me so I can attribute correctly_

There are several on-line write-ups about the Kitchen Analogy. We specifically link to a series of blog-posts on the Kitchen Analogy that were posted on the Intel Developers Site in 2015, as it is one of the most 
well-developed write-ups of the analogy that I have seen thus far:

* [Advanced Computer Concepts for the (Not So) Common Chef: The Home Kitchen](https://software.intel.com/en-us/blogs/2015/05/15/advanced-computer-concepts-for-the-not-so-common-chef-the-home-kitchen)
* [Advanced Computer Concepts for the (Not So) Common Chef: Memory Hierarchy: Of Registers, Cache & Memory](https://software.intel.com/en-us/blogs/2015/06/11/advanced-computer-concepts-for-the-not-so-common-chef-memory-hierarchy-of-registers)
* [Advanced Computer Concepts for the (Not So) Common Chef: The Multi-core Industrial Kitchen](https://software.intel.com/en-us/blogs/2016/07/19/advanced-computer-concepts-for-the-not-so-common-chef-the-multi-core-industrial-0)
* [Pipeline and the Efficient Chef (Part 1)](https://software.intel.com/en-us/blogs/2016/09/26/pipeline-and-the-efficient-chef-part-1)
* [Pipeline and the Efficient Chef (Part 2)](https://software.intel.com/en-us/blogs/2016/10/14/pipeline-and-the-efficient-chef-part-2)

### Variations
Instead of seeing each core as a separate kitchen, it is useful to see each core as a chef with his or her own workstation in a large restaurant. While each chef may have their own personal work area (L1 cache, with cutting board being registers), there may be counter space shared by all the chefs (last level cache). Further away may be a much larger counter top that has all the ingredients the chefs need to prepare the dishes of that day. The pantry (or refrigerator in some write-ups) represents the hard-drive. Note that each level (cutting board, work station, shared chef counter space, ingredients counter top, refrigerator/pantry) represent a _cache_ of all previous levels.

**Differences between volatile/non-volatile memory**:

* Before the restaurant closes at the end of the day, the chefs are required to clean up their station, and put away all ingredients that are out. Likewise, in a computer, all components of the memory hierarchy from the registers through main memory are _volatile_, in that they lose their value when the computer is powered off. 

* Dishes/ingredients stored in the refrigerator/pantry persist even when the restaurant shuts down for the evening. In other words, the refrigerator/pantry is a place for _long term, permanent storage_ and is _non-volatile_. Likewise, the hard-drive retains its data when the computer is powered off. 

**Locality**:

* The more the chef cooks with ingredients that are close by, the faster s/he can make recipes. 
* **Temporal Locality**: An ingredient that a chef used once will likely be used again. (e.g. salt used to adjust the flavor of a dish)
* **Spatial locality**: An ingredient close to another used ingredient will likely be used by the chef (e.g. the pepper and other spices located next to the salt are likely to be used by the chef)

Recipes (programs) that have good locality are easier to make (complete quicker).


**Cache Coherence**:

A danger of having shared work areas is that sometimes values can change. Suppose that Restaurant temporarily has a mouse problem. If a mouse is found on an ingredient/dish, it is "dirty", and it and the things next to it (the mouse could have been there too!) need to be immediately thrown out. Suppose chefs are working together to create a dish. What happens if a mouse is found on one of the shared ingredients? The chef who discovers the mouse will throw out the ingredient and replace it with a fresh one, but how will the other chefs using the same ingredient know that they should replace it? If the oblivious chef continues to cook the dish as normal, the final dish may end up being contaminated. In other words, how do we ensure that all the chefs are using the freshest ingredients, know that their ingredients are indeed fresh?

In a computer, this problem is known as _cache coherence_, in which it is important that all the cores of the system have a consistent view of shared data. In this example, the shared data is the ingredient that was found to have a mouse on it. 

To rectify this situation, the kitchen could have an _inspector_ that monitors the ingredients on the shared table. If they see that one of the shared ingredients have been thrown out, then they let all the chefs who use that table know that the ingredient needs to be replaced. In a computer, this is known as a _snoopy cache_, that snoops on the bus for changes to data. Maintaining a consistent (or coherent) view of shared data is extremely important for systems with many caches.

**False Sharing**:  
Now, suppose the chefs are working together to assemble a smorgasbord, a traditional Swedish meal with many hot and cold food items next to each other on the table. Since this particular smorgasbord is small enough to fit on the 
shared counter-top, the chefs are assembling it there in order to make it faster. Each chef is working on a separate dish that is part of the smorgasbord, and each chef has his or her own ingredients. In other words, the chefs are 
_not_ sharing ingredients or dishes. They are all working on their own component of the smorgasbord.

The inspector is very vigilant for any mice. Remember, if a mouse is found, _all_ of the dishes/ingredients around the mouse must also be discarded. What happens if a pesky mouse is found on one of the dishes of the smorgasbord? In this case, the inspector may not realize that each chef is working on their own dish, and will declare all the dishes as contaminated. Then _all_ the chefs would have to redo the work. Suppose the mouse keeps popping up at various intervals, at different dishes. Instead of the individual dishes being replaced, with every mouse visit, the _entire_ smorgasbord gets replaced every single time, causing the chefs to _thrash_ with anger and frustration, as they are 
not actually sharing any data. 

Likewise, suppose there are a number of threads that are working on populating an array in shared cache, with each thread assigned to a different core. Suppose as well that the array in question fits on a single cache line (analogous to our shared table where the smorgasboad is being assembled). Even though each thread has its own set of elements in the array to update (so there is no data sharing), the snoopy cache sees an update to one element as an update to the entire line in the cache, invalidating all the elements. With every update therefore, the entire array must be thrown out. This illusion that all the threads are sharing data (when in fact they are not) is known as **false sharing**, and can frequently lead to _thrashing_.


---

## CS2013 Knowledge Unit Coverage

### PD/Parallel Architecture

7\. Describe the challenges in maintaining cache coherence. [Familiarity]

### PD/Parallel Performance

4\. Detect and correct an instance of false sharing. [Usage]

6\. Explain performance impacts of data locality. [Familiarity]

---

## TCPP Topics Coverage

### Architecture Topics

* Comprehend Cache organization Know the cache hierarchies, shared caches (as opposed to private caches) result in coherency and performance issues for software

### Programming Topics

* Know Data layout: Know how to lay out data in memory to get improve performance (memory hierarchy)	
* Know Data locality: Know what spatial and temporal locality are, and how to organize data to take advantage of them	
* Know False sharing: Know that for cache coherent shared memory systems, data is kept coherent in blocks, not individual words, and how to avoid false sharing across threads of data for a block

---

## Recommended Courses

* **Systems**: TCPP recommends that cache organization concepts be covered in a systems course.
* **DSA/ProgLang**: TCPP recommends that data layout and locality issues be discussed in either DSA or Programming Languages.

---

## Accessibility

This analogy is fairly visual. If a student has never seen a kitchen, effort must be made before hand to describe the layout of the kitchen

---


## Assessment 

Unknown or unavailable.

---

## Citations
