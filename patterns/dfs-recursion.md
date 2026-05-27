# DFS Recursion

Core Pattern:
node -> recurse left/right -> combine result

Key Insight:
ask:
"what does this function return for this subtree?"

Core Invariant:
every recursive call solves
the same problem for a smaller subtree

Template:

```Java

public int dfs(TreeNode root) {

    if (root == null) {
        return ...
    }

    int left = dfs(root.left);
    int right = dfs(root.right);

    return ...

}
```

Common Uses:

- tree depth
- subtree info
- path calculation
- tree comparison

Signals:

- recursive tree traversal
- subtree
- depth
- height
- balanced
- path

Representative Problems:

- Maximum Depth of Binary Tree
- Balanced Binary Tree
- Diameter of Binary Tree
- Same Tree

Common Pitfalls:

- incorrect base case
- forgetting postorder dependency
- returning wrong subtree info
