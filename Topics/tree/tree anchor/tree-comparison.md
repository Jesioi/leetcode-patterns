# Tree Comparison

Core Pattern:
compare two trees recursively

Key Insight:
current nodes must match
AND
left subtrees must match
AND
right subtrees must match

Template:

return (
p.val == q.val &&
isSameTree(p.left, q.left) &&
isSameTree(p.right, q.right)
)

Signals:

- same tree
- subtree
- symmetric tree

Representative Problems:

- Same Tree
- Subtree of Another Tree
- Symmetric Tree
