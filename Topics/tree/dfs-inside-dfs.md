# DFS Inside DFS

Core:
outer dfs traverses all nodes
inner dfs solves problem from current node

Signal:
every node can be a starting point

Common Structure:

main return (
solveFrom(root) + dfs(root.left) + dfs(root.right)
)

Representative Problems:

- Path Sum III
- Subtree of Another Tree
