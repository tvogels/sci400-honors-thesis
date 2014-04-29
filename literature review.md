
### Lumelsky, Vladimir: Algorithmic and Complexity Issues of Robot Motion in an Uncertain Environment (1987)

* "Path planning is a central problem in robotics"
* There are two types: autonomous vehicles or arm manipulator with fixed base
* Two approaches: path planning with complete information (Piano Movers problem) & path planning with incomplete information (also: dynamic path planning)
* Is about "collison free paths"
* Paper studies algorithmic and complexity issues
* Provable (nonheuristic) and heuristic approaches for incomplete information.
* Complete information: one-time offline
* They have different ways of dealing with it
* Dynamic: on-line, even non-stationary objects
* "Reaching a global goal with local means" is a fundamental problem (maze search, differential games, macroeconomics, collective behaviour, geometry)
* Algorithms can only be judged by: compare to other theoretically feasible algorithms, local optimality, 
* **Previous work on Path Planning with Incomplete Information:**
* Limited to various heuristics. [11-13, 23, 25, 26].
* Typically, objects are approximated by polygons.
* Often, there is a vision module, so in that limited area there is 'complete information'
* Robot arm: 24
* No work has been done on minimum resources that guarantee reasonable navigation.
* Range of applicability of various heuristic procedures is unclear
* Many rely on common sense
* Only non-heuristic algorithm is Pledge, described by Abelson and diSessa: guaranteed convergence, no performance estimates are presented (escape from a maze)
* Dynamic Path planning: no constraints on anything: knows only its coordinates and the coordinates of the target
* Learning yes/no
* "tactile sensors": least informative, only learns about an obstacle when it hits it
* Only two choices: left or right
* Dynamic Path Planning: [28-40]
* Given: **Worst Case Lower bound on the length of the path**
* Given: two basic algorithms for path planning with upper bounds on performance
* Local direction: once and for all determined direction for passing around an obstacle
* *Hit point* and *Leave point*
* What happens when you hit an obstacle tangentially?
* **Like the notation!!** (157)
* Lower bound based on perimeters of obstacles that intersection with a disc around the Target
* Simple algorithm uses 3 registeres to store intermediate information after hitting an obstacle.
* Another simple algorithm remembers start and end point and tries to stay on the line between them
* Bound for convex objects: $P=D+\sum p_i$ and on average $P=D+0.5\sum p_i$.

This is the same as Dynamic Path Planning for a Mobile Automaton with Limited Information on the Environment

### Blum, Navigating in Unfamiliar Geometric Terrain (1991)

* Rectangular obstacles aligned with the axes
* Rectangular obstacles in more general orientations
* Wider classes of convex bodies
* Non-convex obstacles & maze traversal
* Randomized algorithms are provably better than deterministic algorithms
* Unknown scene: [6, 8, 9, 13, 15] 
* Most research has focussed on known scenes
* First for unknown scenes: Papadimitriou and Yannakakis [17]  (not true)! 
* Minimum thickness assumption
* Wall problem: bound of $O(\sqrt{n})$ on the ration $\rho(R,n)$ maching the lower bound of [17]
* Room problem gets $\rho = 2^{c \sqrt{\log n}}$, which is probably not optimal.
* Tight bound of $\Theta(\sqrt{n})$ for point-to-point navigation in scenes with oriented rectangular obstacles.
* Also 3D.
* Squeeze-through assumption.

### Lumelsky, Path-Planning Strategies for A point Mobile Automaton Unknown Obstacles of Arbitrary Shape (1987)

Kind of the same as the first paper ...

### Dynamic Path Planning for a Robot Arm

Arm ...

### Papadimitriou, Shortest paths without a map (1991)

* Shortest paths one of the most well-looked into problems in Computer Science and Operations Research
* Dynamic: both in graphs and geometric scenes
* "Decision making under incomplete information"
* "Techniques developed will add to the scarce rigorous methodological arsenal of AI"
* Two methods presented: seem natural, proven to be optimal in some cases
* "When faced with a block, turn to the nearest corner"
* "Constant ratio cannot be achieved by any method, even with nonintersecting rectangles with sides parallel to the axes"
* For squares of arbitrary size (axis-alligned), we have the ration $\sqrt{26}/3 \approx 1.7$.
* Part 3: Obstacle courses
* Know everything about the obstacle once you encounter it.

### Rao, etc. Robot Navigation in Unknown Terrains (1993)

* Focus on non-heuristic algorithms
* A Taxonomy of Navigation Algorithms: **Class A**: guarantee navigation objective is achieved (early works can be traced back to Sutherland)
* Interest in these works has been rejuvenated by Lumelsky, also maze searching
* **Class B** optimize parameter such as distance travelled
* **Class C** extract basic computational issues: 'finite state automata': can things be solved etc.
* Sensor system: touch vs vision
* INterest in non-heuristic algorithms for navigation in unknown terrains has been rekindled in mid eighties due to the pioneering works of Lumelsky and Stepanov: Bug1 and Bug2
* Extension to Lumelskies algorithms by Sankaranarayanan & Vidyasagar and Sankaranarayanan and Masuda.
* Bug1, Bug2, Alg1 and Alg2 are *metric* algorithms since they use information such as position, distance, etc. 