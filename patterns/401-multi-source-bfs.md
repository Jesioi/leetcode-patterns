# Multi-source BFS

Core Pattern:
BFS expansion from multiple starting points

Core Insight:
All source nodes enter the queue first.
BFS expands outward level by level.

Used for:
minimum distance / minimum time in unweighted graph

Core Components:

- queue
- level traversal
- initialize all sources
- visited marking when enqueue
- process by BFS layer

Template Signal:

- spread over time
- nearest source
- minimum steps
- shortest distance
- simultaneous expansion

Key Question:
What are the starting source nodes?

Common Bugs:

- starting from only one source
- incrementing level incorrectly
- duplicate enqueue
- visited marked too late
- forgetting unreachable nodes

Representative Problems:

- Rotting Oranges
- Walls and Gates
- 01 Matrix
