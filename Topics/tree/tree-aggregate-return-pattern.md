# Tree Aggregate Return Pattern

dfs returns:
current subtree aggregate result

Core structure:

return (
current contribution + left subtree result + right subtree result
)

Examples:

- Count Good Nodes
- Count Univalue Subtrees
- Path Sum III (some versions)

Signal:
subtree needs total count/sum from children
subtree answer = combine children answers + self

## relate question

- Count Good Nodes in Binary Tree
