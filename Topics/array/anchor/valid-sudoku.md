# Valid Sudoku

Pattern:
constraint tracking

Key Insight:
track used values
for row / col / box

Core Structures:
HashSet for:

- rows
- cols
- boxes

Signals:

- validity checking
- constraints
- uniqueness

Complexity:
O(1)

Common Pitfalls:

- incorrect box indexing

Why This Matters:
multi-dimensional hashing intuition
