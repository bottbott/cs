---
lang: en
title: Meet in the Middle
viewport: width=device-width, initial-scale=1.0
---
This is a variation of the Bidirectional A* so that we can **guarantee** that 
the forward and backward searches will open to the same cost. The values in the
priority queue are sorted according to their p-value given by the below 
formula.
$$
p(n) = max(f(n), 2 \cdot g(n))
$$
!!! note
    Nodes are sorted in the list according to the above equation where we take
    the max of the $ f(n) = g(n) + h(n) $ or $ 2 \cdot g(n) $. The 2nd terms 
    job is to prevent the search from crossing the mid point of cost. 

The stopping condition for MM is a little more complex. You can use just the
4th option by itself. $ U $ is the cost of the candidate solution, and it will
stop searching when U meets the below criteria. 

1. \( U \leq g_{\text{minf}} + g_{\text{minb}} + \varepsilon \)
2. \( U \leq f_{\text{minf}} \)
3. \( U \leq f_{\text{minb}} \)
4. \( U \leq \min(p_{\text{minf}}, p_{\text{minb}}) \)
