---
source:https://en.wikipedia.org/wiki/Linked_list
---
What are the tradeoffs of list data structures?
<!--question-->

Property | Linked list | Array | Dynamic array | Balanced tree | Random access list | Hashed array
|-|-|-|-|-|-|-
Indexing | Θ(n) | Θ(1) | Θ(1) | Θ(log n) | Θ(log n) | Θ(1)
Insert/delete at beginning | Θ(1) | N/A | Θ(n) | Θ(log n) | Θ(1) | Θ(n)
Insert/delete at end | Θ(1) when last element is known; Θ(n) when last element is unknown | N/A | Θ(1) amortized | Θ(log n) | N/A | Θ(1) amortized
Insert/delete in middle | search time + Θ(1) | N/A | Θ(n) | Θ(log n) | N/A | Θ(n)
Wasted space (average) | Θ(n) | 0 | Θ(n) | Θ(n) | Θ(n) | Θ(√n)
