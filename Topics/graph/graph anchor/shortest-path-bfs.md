# Shortest Path BFS

Core Pattern:
Find minimum number of steps
in an unweighted graph

Core Insight:
BFS explores nodes level by level.

The first time we reach target,
we have found the shortest path.

Invariant:
All nodes in the same BFS level
have the same distance from start.

Core Components:

- queue
- visited
- level / step count
- neighbor generation

Template Signal:

- shortest path
- minimum steps
- minimum moves
- least transformations
- fewest operations
- unweighted graph

Recognition Signals:

- change one character
- move one step
- open lock
- minimum jumps
- minimum moves
- transform start into target

Key Question:

What can I reach
in one move from current state?

Generate all valid neighbors
and push them into queue.

Common Bugs:

- using DFS instead of BFS
- forgetting visited
- counting steps incorrectly
- checking target too late
- revisiting same state

Representative Problems:

- Word Ladder
- Open the Lock
- Minimum Genetic Mutation

Mental Model:

Level 0:
start

Level 1:
all states reachable in 1 move

Level 2:
all states reachable in 2 moves

...

First time reaching target
= shortest path found
