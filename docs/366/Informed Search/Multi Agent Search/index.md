---
lang: en
title: Multi Agent Search
viewport: width=device-width, initial-scale=1.0
---

## Multi Agent Heuristics
### Makespan
The heuristic is guided by the maximum cost present for all of the agents.
$$
h(s) = max_{a_i \in S}(MD(a_i, g))
$$

$$
h(s) = max_{a_i \in S}(a^*(a_i, g))
$$

### Sum of the Costs
The heuristic is guided by the summation of costs for all of the agents. 
$$
h(s) = \sum_{a_i \in S} (a^*(a_i, g))
$$