# Product of Array Except Self

Pattern:
prefix + postfix accumulation

Brute Force:
multiply every other element

Key Insight:
answer[i] =
left product \* right product

Core Variables:
prefix
postfix

Invariant:
prefix stores left product
postfix stores right product

Complexity:
O(n)

Common Pitfalls:

- off-by-one
- postfix update order

Why This Matters:
builds prefix accumulation intuition
