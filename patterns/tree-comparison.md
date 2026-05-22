# Tree Comparison

Core Pattern:
compare two trees recursively

Key Insight:
trees are equal only if:

- current nodes match
- left subtrees match
- right subtrees match

Template:

boolean same(TreeNode p, TreeNode q) {

    if (p == null && q == null) {
        return true;
    }

    if (p == null || q == null) {
        return false;
    }

    if (p.val != q.val) {
        return false;
    }

    return same(p.left, q.left)
        && same(p.right, q.right);

}

Signals:

- same tree
- subtree
- symmetric tree

Representative Problems:

- Same Tree
- Subtree of Another Tree
- Symmetric Tree

Common Pitfalls:

- missing null checks
- comparing structure incorrectly
