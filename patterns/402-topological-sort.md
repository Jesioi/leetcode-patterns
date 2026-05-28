# Topological Sort

Core Pattern:
Resolve dependency ordering in directed acyclic graph

Core Insight:
A node can only be processed
after its prerequisites are resolved.

Two Main Approaches:

1. BFS / Kahn's Algorithm

- indegree
- queue
- remove edges

2. DFS Cycle Detection

- visiting state
- detect cycles recursively

Core Components:

- adjacency list
- indegree
- queue or DFS state
- cycle detection

Template Signal:

- prerequisites
- dependency graph
- course ordering
- scheduling
- directed graph

Key Question:
Can all nodes be processed without cycle?

Common Bugs:

- reversing edge direction
- forgetting indegree update
- processing node twice
- incorrect cycle state handling
- ignoring disconnected graph

Representative Problems:

- Course Schedule
- Course Schedule II
