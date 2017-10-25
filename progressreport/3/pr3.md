---
author: Andreas Ziegler
title: "Minimal Representation for Collaborative Exploration"
subtitle: "Progress report week 43"
institute: "RPG-UZH"
---

# Summary

Since the last meeting, I tried to get an overview of mesh-approaches. I concentrated my literature review on mesh-approaches, which can be used on mobile robots, run in real-time on a normal CPU and can represent frontiers.

So far I found two lines of research. One is the generation of a mesh for a scene-estimation in real-time, which uses the feature points and the pose estimate of a underlying SLAM system to generate a mesh [@Teixeira2016].

The other line of research uses so called truncated signed distance field (TSDF) [@Curless1996], which stores a discretized estimate of the distance to the nearest surface in the scene. TSDF is another kind of map representation, which is used in robotics for motion planning, mapping, and scene understanding. TSDF uses the output of range sensors e.g. RGB-D cameras rather then feature points as input [@Curless1996]. From the TSDF a mesh can be generated as done in [@Klingensmith2015], [@Oleynikova2017].

The mesh-based scene estimation seems only made for local planning purposes rather than a map representation for future usage. Compared to the mes-based scene estimation, TSDFs seems a widely studied field with a lot of literature and use cases. For example [@Klingensmith2015] mentions different approaches to fuse multiple depth scans into one TSDF. A method how to deform a TSDF based mesh after a loop closure is presented in [@Whelan2013].

However, TSDF is maybe a too complex representation for the purpose of only representing frontiers and a simpler mesh is probably more suitable.

# Conceptual - Minimal representation

## Challenges

* Not reintroducing frontiers in previously visited space
* Deformable after PoseGraph deformation
* Merging after loop closure

## Possible solutions

* Overlap between local maps and information sharing (Choosing a suitable overlap, keep sensor range in mind)
* After a PoseGraph deformation, the nodes of the topological map are updated (the nodes contain the pose). The local maps are relative to the pose of these nodes and therefore the local maps are automatically corrected
* One solution is to combine the frontiers of the two scenes, representing the same location. Another idea is just to keep the one with the bigger frontier.

## Different challenges with occupancy- and mesh-based local map representation

The main difference I currently see is the way how two local maps are merged.

With an occupancy-based representation, frontiers could be merged by simply setting all the cells as frontiers which are frontiers in at least one of the two "source" maps. In a mesh-based representation, either a new mesh is generated from the points of both "source" maps/meshes, the two meshes are merged into one mesh (I don't know how yet) or maybe simply the mesh with the bigger (frontier) surface is kept and the remaining one is removed. 

The other challenges should be independent of the local map representation.

# New ideas

Working with TSDF but this is probably too much for our needs.

# Open questions

* I feel like I still don't know enough about mesh-based approaches for our use case. Hopefully an expert can help.

* Occupancy grid, mesh or TSDF representation for local (metric) maps?

* How to do a proof of concept in 2D and accurately represent the possible problems in 3D, specially for meshes?

# Next steps

* Get a clear view about mesh-based approaches (Probably with the help of an expert)
* Decide whether occupancy, mesh or TSDF based representation
* Work on the proof of concept (Toy example)

# Bibliography
