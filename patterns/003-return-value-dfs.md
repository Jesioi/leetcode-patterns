# Return-value DFS

Core Pattern:
children return information upward

Key Insight:
parent decision depends on subtree results

Core Invariant:
subtree information is fully computed
before parent processes result

Template:

```java
int dfs(TreeNode root) {

    if (root == null) {
        return ...;
    }

    int left = dfs(root.left);
    int right = dfs(root.right);

    return combine(left, right);

}
```

Common Returned Info:

- height
- depth
- subtree size
- valid / invalid state
- max gain from current node
- found node / null

Signals:

- balanced tree
- subtree height
- subtree size
- lowest common ancestor
- maximum path contribution

Representative Problems:

- Maximum Depth of Binary Tree
- Balanced Binary Tree
- Lowest Common Ancestor
- Binary Tree Maximum Path Sum

Common Pitfalls:

- mixing return value with global answer
- returning full path when parent can only use one branch
- forgetting special failure state
- incorrect combine step
- recomputing subtree results

```

```
