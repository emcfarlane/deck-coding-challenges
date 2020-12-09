How do you implement depth-first search?
<!--question-->
Depth-first search (DFS) is a tree and graph traversal search algorithm. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

Worst-case performance: $O(|V| + |E|)$ for explicit graphs traversed without repetition, $O(b^d)$ for implicit graphs with branching factor b searched to depth d

Worst-case space complexity: $O(|V|)$ if entire graph is traversed without repetition, O(longest path length searched) = $O(bd)$ for implicit graphs without elimination of duplicate nodes

### Python
```
def in_order_traversal(self, node, visit_func):
    if node is not None:
        self.in_order_traversal(node.left, visit_func)
        visit_func(node)
        self.in_order_traversal(node.right, visit_func)

def pre_order_traversal(self, node, visit_func):
    if node is not None:
        visit_func(node)
        self.pre_order_traversal(node.left, visit_func)
        self.pre_order_traversal(node.right, visit_func)

def post_order_traversal(self, node, visit_func):
    if node is not None:
        self.post_order_traversal(node.left, visit_func)
        self.post_order_traversal(node.right, visit_func)
        visit_func(node)
```
