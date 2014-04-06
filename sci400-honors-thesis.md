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
* Definitions & Notations
* Outline
* Summary of our results
* My contribution

### Definitions

We investigate a blind robot that navigates in a scene $S$ from the starting point $s$ to a target $t$ which are a distance $n$ apart. 
$S$ contains a finite number of convex inpenetrable obstacles. 
The robot is assumed to be a mobile point automaton that is only aware of its absolute position and the position of $t$. 
It is blind, and only receives sensory feedback when it hits an obstacle. 
It can then follow the edge of the obstacle without knowing about its shape.

The robot will always try to move in a straight line to $t$. When the robot hits an obstacle, it will follow the shape of the object in the direction that initially minimizes the distance to the target until the path to $t$ is clear again. It will repeat its behavior. We assume without loss of generality that if the robot hits the obstacle perpendicularly, the robot moves counterclockwise. This robotic behavior can be categorized as memoryless and dynamic, since it does not plan its path in advance, but decides on its direction every time it touches an obstacle, solely based on its current position, the position of the target and the gradient of the object it hits.

Obstacles may touch each other and the robot is a point, so the robot can "squeeze" through touching obstacles, avoiding the creation of concave objects out of convex ones.

We use a similar notation as (Blum, A., 198x). Let $R(S)$ be the total distance walked by the robot going from $s$ to $t$ in its heuristic path. $d(S)$ denotes the length of the shortest possible path. We are interested in $R(S)$ and will compare it to $d(s)$ and $n$ using two ratios:

[[ \rho = \max_S \frac{R(S)}{d(S)}, \,\,\, \gamma = \max_S \frac{R(S)}{n}. ]]



## Previous research: see papers & abstracts

* What do we do different
* Compare with our results


## Equal Size Squares

This section goes through the earlier work by Henk and Marijke on equal size squares. It basically gives the proof as presented in <code>paper.henk.pdf</code>.


## Circles

This section will only be included if we do not manage to generalize our results to arbitrary convex objects. If we include it, it shows the numerical bounds for the worst-case heuristic paths over the optimal path or distance.


## Similar Same-Orientation *Sharp* Triangles

Asume all obstacles in $S$ to be similar triangles of the same orientation. We use a coordinate system with $t$ in the origin. The sides of triangle $k$ are called $a_k, b_k, c_k$ such that all sides $a_i$ have the same direction $\alpha$, all sides $b_i$ have direction $\beta$ and all sides $c_i$ have direction $\gamma$. For each side-direction $x\in \left\{\alpha,\beta,\gamma \right\}$, we define a half plane $H_x$ that is delimited by a line in the direction $x$ through $t$. It indicates the region in which the robot could hit a triangle at a side in direction $x$. The half planes are well defined because the robot always moves towards $t$.

Next, define ‘axes’. For a direction $x\in \left\{\alpha,\beta,\gamma \right\}$, define $A_x$ as a ray from the origin into $H_x$ that has a direction perpendicular to $x$. By definition, if a the robot hits an obstacle at the $x$-side, it will always be in $H_x$ and decide to move towards $A_x$.

![Illustration](illustration.svg "Illustration of the concepts described above")



### Theorem 1.1

If the robot crosses an axis $A_x$ at a Eudlidian distance $\lambda$ from $t$, it will never cross the same axis at a distance $\geq \lambda$ later in time.


#### Proof

In order to prove theorem 1.1, we start by introducing some concepts that play a role in the argument. First, let's define a custom measurement $M$ for a point's distance to $t$. Let $\Gamma_1$ be a triangle that is similar to and rotated by $180^\circ$ compared to the triangles in $S$. Let $\Gamma_1$ have its orthocenter in $t$ and circumference $1$. Note that the vertices of $\Gamma_1$ are on $A_\alpha,A_\beta$ and $A_\gamma$. The distance $M(p)$ of a point $p$ to $t$ is defined as the factor $f \geq 0$ with which $\Gamma_1$ should be scaled with respect to $t$ such that $p\in\Gamma_1$. 

The heuristic path $HP(s,t)$ crosses the three axes 0 or more times. Let $\textbf{c} = \{c_1,c_2,\ldots\}$ be a vector containing those crossing points and let $A(x_i)$ be the corresponding axes.

Furthermore, for a point $p \in H_x$, define $D_x(p)$ as the $M$-distance between $t$ and the projection of $p$ on $A_x$.

### Lemma 1.1.1

For any direction $x\in\{\alpha,\beta,\gamma\}$ during the heuristic path, $D_x$ can only increase when the path is following the edge of an obstacle and has started following that edge at a point not in $H_x$.

#### Proof

Suppose the heuristic path starts following an edge in the half plane $H_x$  and suppose that $D_x$ increases while following the edge. If the edge is in the $x$-direction, $D_x$ will stay constant. If the edge is not, $D_x$ decreases, since the robot always aims towards $t$. This contradicts the assumptions and proves lemma 1.1.1.


### Lemma 1.1.2
For any $x \not = y$, the intersection $A_x\cap H_y = \{t\}$.

#### Proof
This follows directly from the fact that our obstacles are sharp triangles. For a direction $x\in\{\alpha,\beta,\gamma\}$, the axis $A_x$ is perpendicular to the direction $x$, whereas the angles between $x$ and the other two directions is smaller than $90\deg$.

### Lemma 1.1.3

An obstacle can only be in 2 out of the 3 half planes.

#### Proof

This follows from geometric observations. If the object would be in all three half-planes, it would enclose $t$, which is not allowed.

### Lemma 1.1.4

Let $\Gamma$ be a triangle with sides $a,b,c$ that intersects with the two axes $A_a$ and $A_b$. The intersections of side $c$ with these axes have the same $M$-distance.

#### Proof

This follows from the observation that at $c$, the $M$-measure is by definition constant.


### Lemma 1.1.5

If $M(c_i)=\lambda$ for some $i$, then $M(c_{i+1})<\lambda$ or $M(c_{i+2})<\lambda$.

#### Proof

Consider the edge of obstacle $O_i$. followed after $c_i$. We distinguish two scenarios: (1) after following the edge, the robot is only in one half plane $H_a=H_{A(c_i)}$, and (2) the robot is both in $H_a$ and another half plane $H_b$. 

1. If the robot ends up only in the half plane $H_a$, it can only hit edges in the $a$-direction, and will move towards the axis $A_a$. Since, according to lemma 1.1.1, $D_a$ will decrease, the path will cross $A_a$ again, closer to $t$ than before. $M(c_{i+1})<\lambda$.
2. If the robot ends up in two half planes $H_a$ and $H_b$, it will folow the same obstacle's $b$-side. After following this second side, it can either end up in (1) $H_a \cap H_b$ or (2) in $H_b$ only:
    1. If the robot is still in $H_a \cap H_b$, it did not cross $A_b$ (using lemma 1.1.2). Note that, if $D_b$ would be $\geq \lambda$, the obstacle $O_i$, $O_i$ would intersect with both $A_a$ and $A_b$. This is in contradiction with the observation that the robot did not cross $A_b$. We conclude that at this moment, $D_a < \lambda$ and $D_b < \lambda$. Since those measures monotomely decrease while the robot is in $H_a$ and $H_b$ and the robot now moves towards $A_a$ and $A_b$, it will intersect one of them at $M(c_{i+1})<\lambda$.
    2. If the robot is now only in $H_b$, it will inevitably move towards $A_b$. Following the same argument as directly above, if the robot did not cross the axis, $D_b<\lambda$ and $M(c_{i+1})<\lambda$. Now we consider the case that the robot did cross $A_b$. Due to lemma 1.1.3, the robot is not only in half-plane $H_b$ and will move towards $A_b$. Although its current $D_b$ could be $\geq \lambda$, it will strictly move towards $A_b$. Since by lemma 1.1.4, the part of the axis with $D_b \geq \lambda$ is covered by $O_i$, the robot will now intersect the axis at a distance $M(c_{i+2})<\lambda$.


## Proof Outline (old version)

Proof that for these triangles, the robot will eventually always get there in finite time.

* **Theorem** If the robot crosses an axis $A_x$ at a Eudlidian distance $p$ from $t$, it will never cross the same axis at a distance $\geq p$ later in time.
* Define a metric $M$ with shape of triangle with orthocenter $t$.
* **Lemma** At some point after you crossed an axis at distance $p$ in the $M$ metric, you will cross another axis at a distance $\leq p$ in the $M$ metric, or get to the target.
* **Lemma** After crossing an axis, the projection on axis on both sides decrease monotonely until the robot crosses an axis or reaches $t$. 
* **Lemma** If, after crossing an axis at $M$-distance $p$, another axis is crossed at $M$-distance $\geq p$, it will go back to the axis.
* And then something smart for "and the next round is a big difference". Maybe use space-limitations, but which?
