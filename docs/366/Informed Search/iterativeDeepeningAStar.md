---
lang: en
title: Iterative Deepening A*
viewport: width=device-width, initial-scale=1.0
---
This is a modification to Iterative Deepening Depth First Search to improve 
the time complexity of the search. IDDFS moves somewhat slow as it increments 
its d values. Iterative Deepening A* uses a heuristic to guide the next
d-value. 

The heuristic chooses the next d-value based on the smallest f-value that was 
pruned from the last iteration. 