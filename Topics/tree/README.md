# Tree Patterns

1. Structural DFS
2. Return-value DFS
3. Global-update DFS
4. DFS inside DFS
5. BFS Level Traversal
6. Constraint Propagation DFS
7. Tree Construction DFS
8. BST Inorder Traversal

---

## 1. Structural DFS

top-down traversal

Core Idea:

current node decides recursion flow

Representative:

- Same Tree
- Subtree of Another Tree
- Lowest Common Ancestor
- Invert Binary Tree

---

## 2. Return-value DFS

children return information upward

Core Idea:

parent decision depends on subtree results

Representative:

- Balanced Binary Tree
- Diameter of Binary Tree
- Maximum Depth of Binary Tree
- Binary Tree Maximum Path Sum

---

## 3. Global-update DFS

global variable updated during traversal

Core Idea:

subtree computes value
global answer updates during dfs

Representative:

- Diameter of Binary Tree
- Binary Tree Maximum Path Sum
- Count Good Nodes in Binary Tree

---

## 4. DFS inside DFS

for every node,
start another dfs expansion

Core Idea:

outer dfs traverses start points
inner dfs explores paths

Representative:

- Path Sum III
- Count Good Nodes
- Sum Root to Leaf Numbers

---

## 5. BFS Level Traversal

level-order traversal using queue

Core Idea:

process nodes level by level

Representative:

- Binary Tree Level Order Traversal
- Binary Tree Right Side View
- Binary Tree Zigzag Level Order Traversal

---

## 6. Constraint Propagation DFS

pass valid range/constraint downward

Core Idea:

child nodes inherit parent constraints

Representative:

- Validate Binary Search Tree
- Kth Smallest Element in BST

---

## 7. Tree Construction DFS

rebuild tree recursively from traversal info

Core Idea:

traversal order determines root
recursive partition builds subtrees

Representative:

- Construct Binary Tree from Preorder and Inorder Traversal
- Serialize and Deserialize Binary Tree

---

## 8. BST Inorder Traversal

inorder traversal produces sorted order

Core Idea:

left -> node -> right

Representative:

- Kth Smallest Element in BST
- Validate BST
