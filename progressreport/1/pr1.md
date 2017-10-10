<!-- $theme: default -->

# Map Representations

* Coordinate based
  * Occupancy based 
  * Feature based
    * Geometric (Line, curves, planes)
    * Landmark based
* Relational representation (Graph)
* Combinations

---

# Coordinate based representations

* Can contain detailed information
* Scale bad with the size of the map

---

# Relational based representation

* Mostly do not contain detailed information
* Scale well with the size of the map
* Hierarchical approaches help further reducing required data

---

# Combinations

* Taking the advantages from the coordinate based- and the relational based representation
* Hopefully not inherit their disadvantages
* A graph based representation maybe in combination with some features looks promising

---

# What does exist

* The literature doesn't present that many models
* Generalized Voronoi Graph (GVG) and related extensions are already studied since a few decades
* GVG related literature mostly focuses on range sensors (laser or sonar)
* No collaborative GVG literature found for Robotics

---

# Ideas

* Getting more familiar with GVG
* Investigate GVG creation with RGB-D sensor data
  * Which additional features are required for reliable data association, if any?
  * Approaches for incremental GVG creation exists, but may have to be adapted depending on the additional features
  * What are the minimal required data to incrementally building a map with multiple agents
  * Could a hierarchical model be applied for data association
