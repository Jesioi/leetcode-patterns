# Graph Grid Traversal

Core Pattern:
DFS/BFS traversal on 2D grid

Core Insight:
Each grid cell acts as a graph node.
Neighbor cells are graph edges.

Traversal expands through valid neighboring cells.

Core Components:

- boundary check
- visited marking
- direction traversal
- skip invalid cells

Common Traversal:

- DFS
- BFS

Template Signal:

- island
- connected region
- flood fill
- area counting
- surrounded region

Key Question:
When visiting a cell:

- should I stop?
- should I mark visited?
- should I expand neighbors?

Common Bugs:

- forgetting boundary check
- revisiting cells
- marking visited too late
- row/col confusion
- incorrect direction traversal

Representative Problems:

- Number of Islands
- Max Area of Island
- Flood Fill
- Surrounded Regions
