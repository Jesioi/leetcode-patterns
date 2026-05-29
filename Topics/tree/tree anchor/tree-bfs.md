# Tree BFS

Pattern:
[Pattern BFS](../../../patterns/bfs.md)

Core Pattern:
Queue + level traversal

Key Insight:
process tree layer by layer

Template:

```Java

Queue<TreeNode> q = new LinkedList<>();
q.offer(root);

while (!q.isEmpty()) {
int size = q.size();

    for (int i = 0; i < size; i++) {
        TreeNode node = q.poll();
    }

}
```

Signals:

- level order
- minimum depth
- nearest node
- shortest steps

Representative Problems:

- Binary Tree Level Order Traversal
- Binary Tree Right Side View
- Minimum Depth of Binary Tree
