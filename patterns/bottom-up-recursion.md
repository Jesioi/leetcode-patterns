# Bottom-Up Tree Recursion

Core Pattern:
children return information upward

Key Insight:
parent decision depends on subtree results

Core Invariant:
subtree information is fully computed
before parent processes result

Template:

int dfs(TreeNode root) {

    if (root == null) {
        return ...
    }

    int left = dfs(root.left);
    int right = dfs(root.right);

    return combine(left, right);

}

Common Returned Info:

- height
- balanced status
- path sum
- diameter
- ancestor node

Signals:

- balanced tree
- diameter
- lowest common ancestor
- maximum path

Representative Problems:

- Balanced Binary Tree
- Diameter of Binary Tree
- Lowest Common Ancestor

Common Pitfalls:

- mixing preorder/postorder logic
- recomputing subtree results
- incorrect combine step
