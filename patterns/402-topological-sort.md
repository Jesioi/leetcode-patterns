# Topological Sort

Core Pattern:
Process nodes whose prerequisites
are already satisfied

Core Insight:
A node can be processed only when
all incoming dependencies are resolved

Invariant:
Every node entering queue
has indegree == 0

Primary Approach:

1. Kahn BFS

- indegree
- queue
- remove edges

Recognition Signals:

- prerequisite
- dependency
- build order
- scheduling
- before / after relationship
- directed graph

Key Question:

Can all nodes be processed?

If yes:
Topological ordering exists

If no:
Cycle exists

Common Bugs:

- reversing edge direction
- forgetting indegree update
- only enqueueing one zero-indegree node
- not initializing adjacency list
- ignoring disconnected graph

Representative Problems:

- Course Schedule
- Course Schedule II
- Alien Dictionary
