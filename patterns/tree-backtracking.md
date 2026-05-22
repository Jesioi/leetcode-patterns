# Tree Backtracking

Core Pattern:
build path during DFS
undo state when returning

Key Insight:
current path represents traversal state

Template:

void dfs(TreeNode root) {

    if (root == null) {
        return;
    }

    path.add(root.val);

    dfs(root.left);
    dfs(root.right);

    path.remove(path.size() - 1);

}

Signals:

- root-to-leaf path
- all paths
- path sum
- combinations

Representative Problems:

- Path Sum II
- Binary Tree Paths

Common Pitfalls:

- forgetting to backtrack
- modifying shared list reference
