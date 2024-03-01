---
lang: en
title: Bidirectional Brute Force Search
viewport: width=device-width, initial-scale=1.0
---
The benefit of bidirectional search is that we can try to cut the search space 
in half which gives us big improvements in time and space. We search from the
start to the goal, and from the goal to the start. This particular one is 
implemented with as a variant of Dijkstra's algorithm.

The algorithms are similar except we add the goal to the OPEN and CLOSED lists.
We can stop when we've found the same state in both forward and backward 
search AND!:

$$
\begin{align*}
    n' \text{ the same state in both forward/backward lists} \\
        g_f(n')+g_b(n') \leq g_{minf} + g_{minb} + \epsilon
\end{align*}
$$

Which is to say that the state that the sum of the forward and backward costs
to arrive at that node n is less than or equal to the sum of the smallest 
cost to any node in the forward list and the smallest cost to any node in the 
backward list plus epsilon which is the smallest cost we can incur to move.