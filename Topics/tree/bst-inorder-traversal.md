# BST Inorder Traversal

Signal:
BST + sorted order / kth smallest / kth largest

Core:
inorder = ascending order

Flow:
left
visit root
right

Common bug:
mistake traversal problem for return-value DFS

## Typical Structure

```Java
class Solution {
    int count = 0;
    int res = 0;

    void dfs(TreeNode root) {
        if (root == null) return;

        dfs(root.left);

        // visit current node

        dfs(root.right);
    }
}

```

## Representative Problems:

- Kth Smallest Element in BST
- BST Iterator
- Validate BST (inorder version)
- Convert BST to Greater Tree
