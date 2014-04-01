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
* Previous research
* This project
* Definition
* Outline
* My contribution

### Definitions

A blind robot with GPS navigates from a starting point $S$ to a target $T$. On its way, it encounters obstacles. When the robot hits an obstacle, it will follow the shape of the object in the direction that initially minimizes the distance to the target until it can travel to $T$ in a straight line. We assume without loss of generality that if the obstacle is perpendicular to the straight line between the robot and $T$, the robot moves counterclockwise. Obstacles may touch each other and the robot is a point. The robot can pass between touching obstacles.

We investigate the heuristic path $HP(S,T)$ taken by the robot and compare it to the optimal path $OP(S,T)$ and the distance $d(S,T)$. We denote lengths as $\left|HP(S,T)\right|$.


## Equal Size Squares

This section goes through the earlier work by Henk and Marijke on equal size squares. It basically gives the proof as presented in <code>paper.henk.pdf</code>.


## Circles

This section will only be included if we do not manage to generalize our results to arbitrary convex objects. If we include it, it shows the numerical bounds for the worst-case heuristic paths over the optimal path or distance.


## Similar Same-Orientation Triangles

Asume all obstacles to be similar triangles that have the same orientation. We use a coordinate system with $T$ in the origin. Call the three directions of the sides of the triangles <span style="white-space:nowrap;">$\alpha$,</span> $\beta$ and $\gamma$. Since the robot always moves towards $T$, we can define three overlapping half-planes, $H_\alpha$, $H_\beta$, $H_\gamma$ where each of these half-planes represent the area in which the robot could hit an obstacle at the $\alpha$/$\beta$/$\gamma$ side. The half planes are delimited by a line with the corresponding direction through $T$.

Next, define ‘axes’ $A_\alpha, A_\beta, A_\gamma$ as rays from the origin into $H_\alpha, H_\beta, H_\gamma$, perpendicular to the directions $\alpha, \beta, \gamma$. Take an $x\in \left\{\alpha,\beta,\gamma \right\}$. If the robots hits an obstacle at the $x$-side, it will always be in $H_x$ and move towards $A_x$.
