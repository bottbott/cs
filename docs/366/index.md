---
lang: en
title: CMPUT 366 Notes
viewport: width=device-width, initial-scale=1.0
---

## Search Problem Formation
To formulate a search problem in a state space, we need to have several 
parameters.

- $ G = (S, A) $ A graph with a set of states for the nodes, and edges that define the 
    relations between the nodes.
- $ s_o $ the starting state
- $ s_g $ the goal state
- $ T(s_n) $ the transition function which returns what other states are 
    connected to the input state. 
- $ C(s_n, s_m) $ the cost state which accepts two states and returns the cost
    to connect them. 

When we have this information, we can use various algorithms to search for a 
solution to the problem.

## State Space vs Search Space

```mermaid
graph LR
    A[City A] -- 10 --> B[City B]
    A -- 20 --> C[City C]
    B -- 30 --> D[City D]
    B -- 25 --> C
    C -- 15 --> D
    D -- 50 --> E[City E]
    A -- 60 --> E
```

The above diagram depicts the state space. It shows all of the various the 
different cities you can be in which represent the different states, and it 
shows the edges that relate one state to another. 

```mermaid
graph TD
    A[City A] -->|10| B[ B]
    A -->|20| C[ C]
    A -->|60| E1[ E]
    B -->|30| D1[ D]
    B -->|25| C1[ C]
    C -->|15| D2[ D]
    D1 -->|50| E2[ E]
    C1 -->|15| D3[ D]
    D2 -->|50| E3[ E]
    D3 -->|50| E4[ E]
```

We have a search tree above by selecting City A as the start position and then
calling the transition function recursively until we arrive at a leaf node. 
This could be part of a search problem where we have our state space with nodes
and edges, start node (City A), and goal node (could be City D), and transition
and cost functions. 

## Search Space Size
### Branching Factor
Part of determining the search space size is related to determining the 
number of children a node may have. This is known as the branching factor. 
For example, if we say that generally nodes have 5 child nodes, then the
branching factor is 5. It's typically denoted with $ b $.

![alt text](branchingFactor.png)

### Calculating Search Space Size
We can see from the above search tree that we have:
$$ 3^0 + 3^1 + 3^2 + 3^3 + ... + 3^d $$

And $ 3^d $ is the dominant term which gives the big oh size of the size 
$ O(3^d) $.