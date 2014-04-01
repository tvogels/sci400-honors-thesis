Title:    Autonomous Robot Motion
Author:   Thijs Vogels
Class:    ht
Date:     March 16, 2014
Keywords: computer science, proof, computational geometry
Language: en

# Autonomous Robot Motion
<div class="subtitle">Thijs Vogels</div>


## Introduction

This part will have the following setup:

* Context
* Definition
* Previous research: see papers & abstracts
* What do we do different
* Outline
* My contribution

### Definitions

We investigate a blind robot that navigates in a scene $S$ from the starting point $s$ to a target $t$, which are a distance $n$ apart. $S$ contains a finite number of convex inpenetrable obstacles. The robot is assumed to be a mobile point automaton that is only aware of its absolute position and the position of $t$. It is blind, and only receives sensory feedback when it hits an obstacle. It can then follow the edge of the obstacle without knowing about its shape.

When the robot hits an obstacle, it will follow the shape of the object in the direction that initially minimizes the distance to the target until the path to $t$ is clear again. We assume without loss of generality that if the robot hits the obstacle perpendicularly, the robot moves counterclockwise. Obstacles may touch each other and the robot is a point, so the robot can "squeeze" through touching obstacles, avoiding the creation of concave objects out of convex ones.

We use a similar notation as (Blum, A., 198x). Let $R(S)$ be the total distance walked by the robot going from $s$ to $t$ in its heuristic path. $d(S)$ denotes the length of the shortest possible path. We are interested in $R(S)$ and will compare it to $d(s)$ and $n$ using two ratios:

[[ \rho = \max_S \frac{R(S)}{d(S)}, \,\,\, \gamma = \max_S \frac{R(S)}{n}. ]]


## Equal Size Squares

This section goes through the earlier work by Henk and Marijke on equal size squares. It basically gives the proof as presented in <code>paper.henk.pdf</code>.


## Circles

This section will only be included if we do not manage to generalize our results to arbitrary convex objects. If we include it, it shows the numerical bounds for the worst-case heuristic paths over the optimal path or distance.


## Similar Same-Orientation Triangles

Asume all obstacles in $S$ to be similar triangles of the same orientation. We use a coordinate system with $t$ in the origin. Call the sides of triangle $k$ $a_k, b_k, c_k$ such that all sides $a_i$ have the same direction $\alpha$, all sides $b_i$ have direction $\beta$ and all sides $c_i$ have direction $\gamma$. For each side-direction $x\in \left\{\alpha,\beta,\gamma \right\}$, we define a half plane $H_x$ that is delimited by a line in the direction $x$ through $t$. It indicates the region in which the robot could hit a triangle at a side in direction $x$. The half planes are well defined because the robot always moves towards $t$.

Next, define ‘axes’. For a direction $x\in \left\{\alpha,\beta,\gamma \right\}$, define $A_x$ as a ray from the origin into $H_x$ that has a direction perpendicular to $x$. By definition, if a the robot hits an obstacle at the $x$-side, it will always be in $H_x$ and decide to move towards $A_x$.
