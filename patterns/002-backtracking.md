# Backtracking

Core Pattern:
DFS + choose + explore + undo

Core Insight:
Backtracking explores one possible state path at a time.
After exploring, undo the choice so other branches can reuse clean state.

Mental Model:

choose
→ dfs
→ undo

Core Components:

- path / state
- choice list
- termination condition
- pruning condition
- rollback / undo

Template:

```java
void dfs(...) {

    if (base case) {
        record answer;
        return;
    }

    for (choice : choices) {

        if (invalid choice) {
            continue;
        }

        choose(choice);

        dfs(next state);

        undo(choice);

    }
}
```

Tree Variant:

```java
void dfs(TreeNode root) {

    if (root == null) {
        return;
    }

    path.add(root.val);

    dfs(root.left);
    dfs(root.right);

    path.remove(path.size() - 1);

}
```

Key Question:

Is my visited / path state permanent or temporary?

Signals:

- all combinations
- all permutations
- all subsets
- all paths
- word search
- path sum
- exhaustive search

Representative Problems:

- Subsets
- Combination Sum
- Permutations
- Word Search
- Path Sum II
- Binary Tree Paths

Common Pitfalls:

- forgetting to undo state
- adding shared list reference directly
- stopping too early
- marking visited permanently when it should be temporary
- missing pruning condition
