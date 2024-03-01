---
lang: en
title: Greedy Best First Search
viewport: width=device-width, initial-scale=1.0
---
There are a few ways to modulate the heuristic function to different effect 
such as in weighted A*. Another way is to totally discard the g-cost in the
computation of the f-value and use only the h-value to guide the search.

This algorithm is complete, but sub-optimal. It could find an optimal solution 
but it is not guaranteed to. 

$$
f(n) = h(n)
$$