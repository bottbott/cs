---
lang: en
title: Heuristics
viewport: width=device-width, initial-scale=1.0
---
## Properties

### Admissible
An admissible heuristic function will provide some value $ h(n) $ related to
a given state and the goal state, and that value must **not** exceed the true
optimal path cost from the given state to the goal state. 

$$
h(n) \leq h^*(n)
$$

### Consistent
The use of a queueing structure and the fact that we have to deal with 
transpositions (where multiple pathes may lead to the same state), mean that
it can be possible for an algorithm to try to re-open nodes that have already
been added to the **OPEN** list. We need the heuristic function.... FINISH.

## Functions
### Manhattan Distance
### Octile Distance
### Tiles Out of Place
### Pattern Databases
