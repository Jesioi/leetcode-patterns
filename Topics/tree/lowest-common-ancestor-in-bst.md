# Lowest Common Ancestor in BST

Pattern:
Constraint propagation / BST property

Core Insight:
If p and q are both smaller than root, LCA is in left subtree.
If p and q are both larger than root, LCA is in right subtree.
Otherwise root is the split point, so root is LCA.

Do not use normal Binary Tree LCA here.
BST lets you choose only one side.
