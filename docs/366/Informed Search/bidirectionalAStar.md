---
lang: en
title: Bidirectional A*
viewport: width=device-width, initial-scale=1.0
---
This builds upon what we have see with Bidirectional Brute Force with 
Dijkstra'a algorithm, but also makes use of A* heuristic functions. The 
downside to this is that the opening of nodes may not be balanced between the
forward and backward lists, and the whole point of bidirectional search is to 
ideally cut the search space in half. This is solved in 
[Meet in the Middle](meetInTheMiddle.md). In general, Bidirectional A* does 
meet in the middle, but if you need to be certain use MM. 

