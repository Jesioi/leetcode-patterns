# Graph Grid Traversal

Core Pattern:
DFS/BFS traversal on 2D grid

Core Insight:
grid cell = graph node
4 directions = edges
must track visited

Core Components:

- boundary check
- visited marking
- direction traversal

Typical Signals:

- islands
- connected regions
- flood fill
- area counting

Mental Model:

find one node
→ consume entire connected component

```java
void dfs(...) {

    if (invalid || visited) {
        return;
    }

    markVisited();

    dfs(neighbor1);
    dfs(neighbor2);
    dfs(neighbor3);
    dfs(neighbor4);
}
```

Common Bugs:

- revisit node
- boundary overflow
- forgetting visited
- modifying grid incorrectly

Representative Problems:

- Number of Islands
- Max Area of Island
- Flood Fill
