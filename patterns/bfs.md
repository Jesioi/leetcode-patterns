# Breadth First Search (BFS)

Core Pattern:
process nodes level by level using queue

Key Insight:
queue preserves traversal order

Core Invariant:
all nodes currently in queue
belong to the current/future levels

Template:

Queue<TreeNode> q = new LinkedList<>();
q.offer(root);

while (!q.isEmpty()) {

    int size = q.size();

    for (int i = 0; i < size; i++) {

        TreeNode node = q.poll();

        if (node.left != null) {
            q.offer(node.left);
        }

        if (node.right != null) {
            q.offer(node.right);
        }
    }

}

Signals:

- level order
- minimum steps
- shortest path
- nearest node

Representative Problems:

- Binary Tree Level Order Traversal
- Binary Tree Right Side View
- Minimum Depth of Binary Tree

Common Pitfalls:

- forgetting level size loop
- mixing DFS recursion with BFS logic
