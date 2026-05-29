# Tree DFS

Pattern:
[Pattern dfs top down](../../../patterns/dfs-recursion.md)

## 1. Void DFS (Top-down)

Core Idea:

parent passes state to child

### Pattern

```java
void dfs(TreeNode node, State state) {
    if (node == null) return;

    // process current node
    // update state / global answer

    dfs(node.left, newState);
    dfs(node.right, newState);
}
```

### Mental Model

```text
state goes downward
```

### Common Signals

- traversal
- path
- current sum
- modify tree
- global variable
- build path/string

### Representative Problems

- Binary Tree Paths
- Path Sum
- Invert Binary Tree
- Flatten Binary Tree

---

## 2. Return-value DFS (Bottom-up)

Core Idea:

child returns answer to parent

### Pattern

```java
Type dfs(TreeNode node) {
    if (node == null) return base;

    Type left = dfs(node.left);
    Type right = dfs(node.right);

    return combine(left, right);
}
```

### Mental Model

```text
answer goes upward
```

### Key Question

```text
What does this function return for this subtree?
```

### Common Signals

- depth
- subtree
- balanced
- same tree
- validate
- count
- diameter

### Representative Problems

- Maximum Depth of Binary Tree
- Same Tree
- Balanced Binary Tree
- Subtree of Another Tree
- Validate BST
- Diameter of Binary Tree

---

## Quick Distinction

### Void DFS

```text
pass state downward
```

### Return-value DFS

```text
return subtree answer upward
```
