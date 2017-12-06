---
author: Andreas Ziegler
title: "Minimal Representation for Collaborative Exploration"
subtitle: "Progress report week 47"
institute: "RPG-UZH"
---

# Summary

Since the last meeting, I mainly worked on the demo. I fixed the rotation noise, changed the camera to work in the local frame and finished the information filtering. I also worked on a polygon ray intersection approach for the polygon merging, which we decided to stop for the moment due to the high complexity and probably a lot of special cases which would have to handle. Instead we now try a polygon intersection approach for the polygon merging. The polygon intersection approach has the advantage, that we always have a polygon, that is guaranteed to be closed.

I also started to install FLaME [@Greene2017] for which I have to check some library dependencies.


# New ideas
While searching for a library, capable of finding polygon intersections, I came across the python library shapely which supports different shapes such as lines and polygons and that provides the functionalities of creating the union, intersection, etc. of two shapes e.g. polygons. I therefore will use shapely for the polygon intersection approach.

<!--# Open questions-->

# Next steps

* Work on the polygon merge approach
* Get FLaME running

# Bibliography
