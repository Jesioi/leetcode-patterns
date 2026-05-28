# Graph Cloning

Core Pattern:
DFS/BFS + old-to-new node mapping

Core Insight:
Graphs may contain cycles.
Each node must be cloned exactly once.

Core Components:

- hashmap<old, new>
- recursive DFS or BFS
- reuse existing clone
- clone neighbors

Template Signal:

- deep copy graph
- preserve graph structure
- cyclic references
- graph node neighbors

Key Question:
Have I already cloned this node?

Common Bugs:

- infinite recursion
- duplicate cloned nodes
- shared original references
- forgetting neighbor cloning

Representative Problems:

- Clone Graph
