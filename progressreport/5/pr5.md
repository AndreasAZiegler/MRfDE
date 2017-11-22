---
author: Andreas Ziegler
title: "Minimal Representation for Collaborative Exploration"
subtitle: "Progress report week 45"
institute: "RPG-UZH"
---

# Summary

Since the last meeting, I improved the 2D simulation environment for a proof of concept and started with a mesh fusion approach. Next to the recommended papers [@Weiss2011] and [@Greene2017], I also read [@Zhou2013], [@Zhou2016] and [@briales17CVPR] which I found while searching for mesh alignment approaches. Whereas in [@Weiss2011] and [@Greene2017] different mesh construction algorithms are proposed, [@Zhou2013] discusses an approach how different meshes can be aligned by using a global registration algorithm. There is also a C++ implementation available of this approach. [@Zhou2016] and [@briales17CVPR] provide two state-of-the-art global registration algorithms which seem to work in real-time. The first also provides a C++ implementation and the latter a Matlab implementation, which depends on CVX. With the above mentioned literature I think I have now already a bit a clearer idea, how meshes can be created and merged.

# New ideas
The ideas/implementation of the above mentioned literature could be a way to go in the 3D case.

<!--# Open questions-->

# Next steps

* Finish mesh merging in proof of concept
* Try different maps and trajectories

# Bibliography
