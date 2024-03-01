---
lang: en
title: General Properties
viewport: width=device-width, initial-scale=1.0
---
There are several properties of search algorithms that are of interest to us. 

## Complete
For an algorithm to be complete, it must always be able to find a solution if
a solution exists for a problem. 

## Optimal
An algorithm may find many candidate solutions to a problem, but it must be 
able to determine which one is the best of all the possible solutions. We are
often looking for the presence of the shortest path, and an optimal algorithm
will find it. 

Suboptimal algorithms will be useful to us when an optimal algorithm exists, 
but its implementation is too costly. 

## Space Complexity
Search algorithms need to open up nodes as they explore their neighbours and 
this takes up space. See the branching diagram on the [main page](index.md).

## Time Complexity
The amount of time it will take us to search also depends on the number of 
nodes that are opened up/expanded. See the same branching diagram. 