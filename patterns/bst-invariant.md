# BST Invariant

Core Invariant:
left < root < right

Key Insight:
inorder traversal of BST
produces sorted order

Template:

inorder(left)
visit(root)
inorder(right)

Common Uses:

- kth smallest
- validate BST
- sorted traversal
- predecessor/successor

Signals:

- binary search tree
- sorted tree
- kth smallest/largest

Representative Problems:

- Validate Binary Search Tree
- Kth Smallest Element in BST

Common Pitfalls:

- checking only direct children
- forgetting global min/max bounds
