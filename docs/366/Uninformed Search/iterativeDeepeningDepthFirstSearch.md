---
lang: en
title: Iterative Deepening Depth First Search
viewport: width=device-width, initial-scale=1.0
---
IDDFS resolves the problems with Depth First Search where DFS goes further 
than the depth at where the solution state is. It does this by incrementing
the depth of its search and doing all of the expansions until this limit. 
That way we can be sure to  find an optimal solution. 