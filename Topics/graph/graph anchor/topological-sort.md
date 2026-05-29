# Topological Sort

Core Pattern:
dependency ordering in DAG

Core Insight:
node can only be processed
after prerequisites are resolved

Core Components:

- indegree
- adjacency list
- queue

Typical Signals:

- prerequisites
- dependency graph
- ordering constraints
- cycle detection

Common Bugs:

- forgetting indegree update
- processing node twice
- not detecting cycles

Representative Problems:

- Course Schedule
- Course Schedule II
