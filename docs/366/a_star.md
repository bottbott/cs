---
lang: en
title: A* Search
viewport: width=device-width, initial-scale=1.0
---
A* Search is an improvement on [Dijkstra's algorithm](../dijkstra#Algorithm) to help increase the speed
of the search by creating a focused search frontier. 

The priority queue receives a different cost value. Dijkstra's algorithm only
adds the current cost leading up to the particular node, but A* adds an
additional heuristic cost between the current node and the end node. 

A* follows the same algorithm as Dijkstra's with a couple of exceptions. We
have access to the g-value and h-value[^ghvalues].

[^ghvalues]:
    {-} The g-value is the calculated cost from the start node to a node. The 
    h-value is the heuristic derived cost from the node to the finish.

- We use the f cost to sort the priority queue \(f = g + h\)
- Nodes that are expanded with a sub-optimal cost will eventually be re-opened
however many times until the optimal cost is found.

In Dijkstra we made updates when we found a better g-value for a given node.
For A*, we will update this when we find a better f-value. 