---
lang: en
title: Heuristics
viewport: width=device-width, initial-scale=1.0
---
## Properties

### Admissible
An admissible heuristic function will provide some value $ h(n) $ related to
a given state and the goal state, and that value must **not** exceed the true
optimal path cost from the given state to the goal state. Admissible heuristics
are able to find the optimal path to the goal state if it exists.

$$
h(n) \leq h^*(n)
$$

### Consistent
The use of a queueing structure and the fact that we have to deal with 
transpositions (where multiple pathes may lead to the same state), mean that
it can be possible for an algorithm to try to re-open nodes that have already
been added to the **OPEN** list. A heuristic that is consistent will never
re-open nodes.

## Functions
### Number of Tiles Out of Place
This heuristic is used in the sliding tiles game. The heuristic function will
count the number of tiles that are not in their correct position. 
### Manhattan Distance
### Octile Distance
### Tiles Out of Place
### Pattern Databases
This heuristic is applied in a sliding tiles game and could be used in other
combinatorial problems. The basic idea is to simplify the game into a goal
state mask and then apply your actions to this mask. This forms its own state
space and the costs related to arriving at each state from the series of actions.
Those costs can be used as your heuristic values in your main search. 