# Backtracking on Grid

Core Pattern:
DFS + path state + undo

Core Insight:
explore path recursively
then restore state after exploration

Core Components:

- visited marking
- recursive exploration
- state rollback

Typical Signals:

- path search
- word matching
- maze traversal
- exhaustive exploration

Common Bugs:

- forgetting rollback
- shared state corruption
- incorrect visited timing

Representative Problems:

- Word Search
- Word Search II
