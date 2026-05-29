# Return-value DFS (Bottom-up)

Pattern:
[Patterns bottom up recursion](../../../patterns/bottom-up-recursion.md)

Core Pattern:

children return information upward

Key Insight:

parent decision depends on subtree results

### Key Question

```text
What does this function return for this subtree?
```

### Pattern

```java
Type dfs(TreeNode node) {
    if (node == null) return base;

    Type left = dfs(node.left);
    Type right = dfs(node.right);

    return combine(left, right);
}
```

### Common Returned Info

- depth / height
- balanced status
- subtree validity
- path sum
- ancestor node
- diameter

### Signals

- subtree
- balanced tree
- diameter
- lowest common ancestor
- same tree
- validate BST
- max path

### Representative Problems

- Maximum Depth of Binary Tree
- Balanced Binary Tree
- Diameter of Binary Tree
- Lowest Common Ancestor
- Same Tree
- Subtree of Another Tree
- Validate BST
