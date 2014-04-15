
# Autonomous Robot Motion 

Thijs Vogels, Honors Thesis 2014

Current studies into robotic motion focus mainly on developing methods for robots to learn about their surroundings and to navigate efficiently through the saved environment. For this project, we go back to the basics. We study automata of the simplest kind: point-robots that only know their coordinates and the coordinates of a target. Furthermore, they sense whether they hit an unknown object on their path. The automata do not store any information in local memory.

We investigate the behavior of the robot when it always tries to travel to its target in a straight line. If it hits an obstacle, it will take the direction that initially seems to minimize the distance to the target. The heuristic path taken by the robot is not necessarily optimal. We compare the length of the heuristic path to the optimal path and to the distance between starting point and the target. For the case of similar same-orientation triangles, we prove that in this way, the robot will always be able to reach the target and in the case of axis-aligned rectangles, we provide an upper bound on the ratio "heuristic path"/"optimal path".