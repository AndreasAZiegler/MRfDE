<!-- $theme: default -->

# <center>Pose-graph-based representation for exploration</center>
# <center>-</center>
# <center>current project state</center>

---
<!-- page_number: true -->
# Motivation

 * Most current exploration methods are based on grid-based representations
 * These representations assume a perfect state estimate
 * Not realistic for visual(-inertial) odometry, which produces a pose-graph exhibiting drift
 * We seek a pose-graph-based representation for exploration

---

# Frontier-based exploration

 * Represent map as obstacles and frontiers
   * A frontier is the border between known / unknown space
 * Exploration is finished when there are no more frontiers
 * Robots have to share frontiers and the information how to go there

---

# Approach - Mesh / Polygon

* Edges represent <span style="color:blue">frontiers</span> or <span style="color:red">obstacles</span>
* Free space is inside the polygon
<center><img src="./polygon.png" height="300"/></center>

---

# Why is this better than a grid?

 * Naturally deformable with the pose graph
<center><img src="./polygon-uncorrected.png" height="360"/><img src="./polygon-corrected.png" height="360"/></center>

---

# Active area

 * The active area is a local area within which the drift is small
 * Polygons within the active area are related
   * Overlapping polygons only get merged if they are in an active area
 * This prevents merging of unrelated polygons
   * Good for noisy estimates

<!--<center><img src="./active-area.png" height="450"/></center>-->

---

# Active area

 * This prevents merging of unrelated polygons
   * Good for noisy estimates
<center><img src="./active-area.png" height="450"/></center>

---

# How to merge if it should actuallly overlap?

 * Merge polygon if SLAM system detected a loop closure:
   * Correct polygon according the corrected pose graph
   * Merge active areas
   * Merge polygons
 
 https://youtu.be/br5jlRJMpD0

<!--<center><img src="./loop-closure.png" height="460"/></center>-->