# Graph Cloning

Core Pattern:
DFS/BFS + old-to-new mapping

Core Insight:
graph may contain cycles
must memoize cloned nodes

Core Components:

- hashmap<old, new>
- visited memoization
- recursive cloning

Typical Signals:

- deep copy graph
- preserve structure
- cyclic references

Common Bugs:

- infinite recursion
- duplicate cloning
- shared reference bugs

Representative Problems:

- Clone Graph
