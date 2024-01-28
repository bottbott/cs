---
lang: en
title: Dijkstra
viewport: width=device-width, initial-scale=1.0
---
# Algorithm
```python
def dijkstra(s0, sg, T):
    OPEN.append(s0)
    CLOSED.add(s0)
    while not OPEN.empty():
        n = OPEN.pop()
        if n == sg:
            return path from s0 to n
        for n′ in T(n): 
            if n′ not in CLOSED:
                OPEN.append(n′)
                CLOSED.add(n′)
            # if it has found better path
            if n′ is in CLOSED and g(n′) < CLOSED[n′].g_value:
                update g(n′) in OPEN and CLOSED
                update parent of n′in CLOSED
                #reconstruct entire heap
                heapify OPEN
```

# Details
The main function if the inner loop has two parts:
- if the child wasn't in the CLOSED list (if we haven't seen it before). Then
add it to the CLOSED list.
- if that child has a cheaper cost than the current version in the CLOSED list,
then update it to that value. 