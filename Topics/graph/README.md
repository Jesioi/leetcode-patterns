# Graph Patterns

1. Graph Traversal
2. Cycle Detection
3. Topological Sort
4. Shortest Path
5. Union Find

## 1. Graph Traversal

- DFS

  - stack/ recursion stack

- BFS traversal

  - BFS 的核心数据结构就是 queue
  - 几乎可以记成是 BFS 就用 queue

- visited

- connected component

Representative:

- Number of Islands
- Clone Graph
- Max Area of Island
- Flood Fill

---

## 2. Cycle Detection

detect revisit in current path

Representative:

- Course Schedule
- Graph Valid Tree

---

## 3. Topological Sort

两个写法：

1. BFS Kahn's Algorithm

   - queue + indegree

2. DFS Cycle Detection

   - visited
   - visiting
   - visited-done

dependency ordering

Representative:

- Course Schedule II
- Alien Dictionary

---

## 4. Shortest Path

minimum distance/path

Representative:

- Rotting Oranges
- Word Ladder
- Dijkstra later

---

## 5. Union Find

dynamic connectivity

Representative:

- Number of Connected Components
- Redundant Connection
