How do you implement breadth-first search?
<!--question-->
Breadth-first search (BFS) is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root (or some arbitrary node of a graph, sometimes referred to as a 'search key'), and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level.

## Complexity

Worst-case performance: $O(|V|+|E|)=O(b^{d})$

Worst-case space complexity: $O(|V|)=O(b^{d})$

The time complexity can be expressed as $O(|V|+|E|)$, since every vertex and every edge will be explored in the worst case. $|V|$ is the number of vertices and $|E|$ is the number of edges in the graph. Note that $O(|E|)$ may vary between $O(1)$ and $O(|V|^{2})$, depending on how sparse the input graph is.

