---
author: Andreas Ziegler
title: "Minimal Representation for Collaborative Exploration"
subtitle: "Progress report week 42"
institute: "RPG-UZH"
output: pdf_document
csl: ieee.csl
bibliography: pr1.bib
---

# Summary

After the last meeting, where we discussed the limitations of the GVG, I looked in the literature for use cases, where the GVG is applied in general unstructured environments. The only literature I found, used the GVG in 2D indoor environments like offices. Therefore, I decided to not longer investigate the GVG and to look into the other directions, which we discussed during the last meeting.

I spent some time to check, if there are already some publications, which work towards the same goal or something similar as we. The majority of research regarding collaborative exploration uses a (complete) map, shared by all the robots [@Burgard2002], [@Burgard:2005:CME:2211641.2211744], [@Bautin2012], and often assumes, knowing the position of the other robots [@Burgard:2005:CME:2211641.2211744], [@Bautin2012]. Another approach I found [@7402164], doesn't share any information regarding the frontiers with others and instead uses an utility function, which penalizes frontiers, which are close to other robots.

Next, I looked further into hybrid metric-topological map representations. There is quite some work, using such hybrid representations [@Bosse2003], [@Blanco2007], [@Pedraza2008] with the primary goal to keep the computational complexity and the memory requirements low. Hybrid metric-topological map representations are mostly used for SLAM but are also applied for exploration.

There is not much work on mesh-based scene representation for real-time usage. The work done in [@Teixeira2016] looks promising as the goal is an estimation of the immediate surroundings in real-time rather than a detailed scene representation. Also the idea of "free curve", "solid curve" and the "Save Region", proposed in [@Gonzalez-Banos2002] is interesting. A mesh-based representation could be seen as a 3D extension of the "free curve" and "solid curve" approach.

# New ideas
As stated in the [Summary], hybrid representations are used and give good results. One approach is, that nodes contain a local (metric) map, local features or a local mesh and the edges contain the transformation between the nodes. When the transformation between two nodes is also represented locally, then these transformations shouldn't be affected by a lot of drift.

With such a hybrid map representation, a robot only has to share the nodes and edges with another robot, which it actually needs to reach a certain location and not the whole map. Another advantage of a hybrid map representation is, that a global optimization shouldn't be necessary after e.g. a loop closure and only the affected local representation and edges have to be adjusted.

Regarding the planning, where and when to create a new node, there are multiple strategies:

* Overlapping maps at a fixed distance threshold (as in [@Furgale2010])
* When a map exceeds a number of feature points (as in [@Bosse2003] and [@Pedraza2008])
* Next best view planner (utility function) to decide where the next node should be (considering enough overlap) (as in [@Gonzalez-Banos2002] and [@Akdeniz2015])

<!-- Local mesh / features links to node, in which it was created / first seen. If the location of a node changes e.g. after loop closure, mesh or features will be corrected according to the difference. Also the transformation contained in the edges will be updated.-->

# Open questions

* Which local (metric) representation is the best for our purpose?
    * Is the local representation only used for frontier representation or also for localization?
* What is the best approach, to decide where the next node should be created / the next observation should be made?
* How to merge meshes? Do they need to be rebuilt?

# Next steps

* Investigating mesh-merge (for frontier representation)

* Proof of concept for hybrid map representation, after the open questions are answered. A proof of concept may allow us to answer the following questions:
    * Does the local (metric) representation work?
    * How much information has to be shared?
    * Does localization work?
    * Is it possible to correct the map and how about the complexity?

# Bibliography
