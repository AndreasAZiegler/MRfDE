---
author: Andreas Ziegler
title: "Minimal Representation for Collaborative Exploration"
subtitle: "Progress report week 41"
institute: "RPG-UZH"
output: pdf_document
csl: ieee.csl
bibliography: pr1.bib
---

# Summary
So far I mainly read literature related to different map representations and exploration approaches. I believe, I have now an overview of the different map representations and their advantages as well as disadvantages. The different map representations can be summarized in two main groups with subgroups and combinations thereof [@Wallgrun2010]:

* Coordinate based
    * Occupancy based 
    * Feature based
        * Geometric (Line, curves, planes)
        * Landmark based
* Relational representation (Graphs)
* Combinations

The advantage of coordinate based map representation is that they can contain detailed information of the environment. This comes at the cost of the data size which can become large, specially when dealing with big maps. Therefor, coordinate based map representations scale not well with the size of the map.

Relational map representations mostly don't contain very detailed information of the environment. This results in a map representations which scale well with the size of the map as they don't consume that much storage space. Hierarchical approaches can further help to reduce the amount of data to deal with [@Wallgrun2010]. Relational map representations can also be annotated with further information, such as local features.

A line of research [@Bosse2003], [@Lisien2005] uses hierarchies of relational map representations or a combination of relational representation and coordinate based representation. This approaches are taking the advantages from both representations while trying to not inherit their disadvantages. A graph based representation in combination with some local features looks like a promising approach.

There aren't that many relational based map representation in the literature. The most prominent is the Generalized Voronoi Graph (GVG) and related extensions, which seems well studied [@Wallgrun2010], [@Lisien2005], [@Choset2001] and [@Tao2011].

The GVG consists of nodes and edges. Nodes of the GVG are either meet points, the set of points equidistant to three or more obstacles, or boundary points, where the distance between two obstacles equals zero. These nodes are connected by edges which are paths of two-way equidistance to obstacles that are also feasible paths between meet-points [@Tao2011]. An example of a GVG is shown in \autoref{fig:gvg}.

![An example of a GVG (taken from [@Tao2011])\label{fig:gvg}](GVG.png){ width=50% }

The GVG is a topological representation of an environment that can be incrementally constructed with a mobile robot using sensor-based control [@Tao2011]. Construction the GVG is akin to provably complete exploration because once the robot knows the GVG it can plan a path between any two location [@Choset2001]. Therefore the GVG seems to be a good map representation for exploration tasks.

The GVG related literature mostly uses range sensors such as laser scanners or sonar to obtain the distances to the obstacles, which is a key point to construct a GVG [@Tao2011]. Constructing a GVG with visual information e.g. from RGB-D sensors is not covered in the literature. Also literature regarding the collaborative construction of GVG's with multiple agents seems not to exist yet.

Using a GVG to represent a map for exploration purposes looks like a good approach and is also mentioned in the literature [@Tao2011], [@Choset2001].

# New ideas
As the construction of a GVG from visual information eg. from RGB-D sensors is not yet covered in the literature, this could be a first idea to investigate.

The problem of data association within the GVG and the incremental construction of a GVG is theoretically described in [@Wallgrun2010] but seems not yet applied to a system with multiple agents. Therefore this could also be an idea worth to further investigate.

# Open questions
* How can I print documents in the lab?

# Next steps
* Getting more familiar with GVG
* Investigate GVG creation with RGB-D sensor data
    * Which additional features are required for reliable data association, if any?
    * Approaches for incremental GVG creation exists, but may have to be adapted depending on the additional features
    * Could a hierarchical model be applied for data association

# Bibliography
