---
lang: en
title: Data Structures
viewport: width=device-width, initial-scale=1.0
---
# Priority Queue with heapq
We use the heapq library in Python as our base class for a priority queue.

## Methods
- .heappush - add an item to the heap. 
- .heappop - removes the item at the top of the heap.

## Indexing
You can index into the heap the same way you can for other collections; 
however, the only thing that is guaranteed is that the min/max will be in the 
zero position [0]. 