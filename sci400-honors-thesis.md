Title:    Autonomous Robot Motion
Author:   Thijs Vogels
Class:    ht
Date:     March 16, 2014
Keywords: computer science, proof, computational geometry
Language: en

# Autonomous Robot Motion
<div class="subtitle">Thijs Vogels</div>


## Definitions

A blind robot with GPS navigates from a starting point $S$ to a target $T$. On its way, it encounters obstacles. When the robot hits an obstacle, it will follow the shape of the object in the direction that initially minimizes the distance to the target until it can travel to $T$ in a straight line. We assume without loss of generality that if the obstacle is perpendicular to the straight line between the robot and $T$, the robot moves counterclockwise. Obstacles may touch each other and the robot is a point. The robot can pass between touching obstacles.

We investigate the heuristic path $HP(S,T)$ taken by the robot and compare it to the optimal path $OP(S,T)$ and the distance $d(S,T)$. We denote lengths as $\left|HP(S,T)\right|$.


## Similar Same-Orientation Triangles

Asume all obstacles to be similar triangles that have the same orientation. We use a coordinate system with $T$ in the origin. Call the three directions of the sides of the triangles <span style="white-space:nowrap;">$\alpha$,</span> $\beta$ and $\gamma$. Since the robot always moves towards $T$, we can define three overlapping half-planes, $H_\alpha$, $H_\beta$, $H_\gamma$ where each of these half-planes represent the area in which the robot could hit an obstacle at the $\alpha$/$\beta$/$\gamma$ side. The half planes are delimited by a line with the corresponding direction through $T$.

Next, define ‘axes’ $A_\alpha, A_\beta, A_\gamma$ as rays from the origin into $H_\alpha, H_\beta, H_\gamma$, perpendicular to the directions $\alpha, \beta, \gamma$. Take an $x\in \left\{\alpha,\beta,\gamma \right\}$. If the robots hits an obstacle at the $x$-side, it will always be in $H_x$ and move towards $A_x$.

Mauris ac eros. Donec quis lacus. Nam et lacus. Mauris in orci a dolor placerat sollicitudin. Vivamus sollicitudin, nibh ac consectetuer auctor, quam massa volutpat leo, id ornare nunc nisi nec lacus. Aliquam sit amet lectus ac turpis cursus tempus. Sed sit amet purus et mi ultrices laoreet. Sed pretium. In tempor dapibus tortor. Etiam lacinia risus non dui. Duis libero arcu, convallis vel, adipiscing ut, pellentesque sit amet, metus. Nulla facilisi. Sed pharetra, urna vitae nonummy hendrerit, elit massa ultrices lacus, non suscipit enim pede ac enim. Nam arcu urna, fermentum non, lacinia ut, commodo id, nisi. Suspendisse odio urna, mollis vitae, pretium in, porta in, ligula. Fusce neque felis, posuere quis, ultrices eu, mollis a, turpis. Praesent sem urna, semper quis, sollicitudin vel, commodo sit amet, enim. Fusce semper sem vel ipsum. Vivamus et massa. Mauris pretium blandit lorem.

Nullam varius, quam eget tempus fermentum, felis massa feugiat est, ac lacinia nisi leo ac sapien. Nullam eu odio ultrices pede rutrum faucibus. Nam nonummy placerat risus. Phasellus dictum blandit tortor. Vivamus a lectus. Ut ligula nibh, sodales pellentesque, lacinia sed, luctus at, ipsum. Curabitur ornare. Sed magna erat, sagittis eget, volutpat sit amet, sodales nec, quam. In lobortis porttitor odio. Donec nunc. Donec tristique ornare eros. Mauris id urna et augue facilisis dictum.