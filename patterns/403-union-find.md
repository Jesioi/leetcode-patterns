# Union Find

Core Pattern:
Track connected components dynamically

Core Insight:
Each connected component has a representative parent.

Core Components:

- parent array
- find()
- union()
- path compression
- optional union by rank

Used For:

- connectivity
- cycle detection
- grouping components

Template Signal:

- connected components
- same group
- redundant edge
- dynamic connectivity
- undirected graph cycle

Key Question:
Do these nodes already belong to the same component?

Common Bugs:

- unioning non-root nodes
- missing path compression
- incorrect parent update
- off-by-one indexing
- forgetting cycle condition

Representative Problems:

- Redundant Connection
- Number of Connected Components in an Undirected Graph
- Graph Valid Tree
