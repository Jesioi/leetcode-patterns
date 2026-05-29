# Longest Consecutive Sequence

Pattern:
hash set sequence expansion

Brute Force:
sort array first

Key Insight:
only start counting
when num - 1 does not exist

Invariant:
every sequence counted once

Core Condition:
if (!set.contains(num - 1))

Complexity:
O(n)

Common Pitfalls:

- recounting same sequence repeatedly

Why This Matters:
teaches optimization through sequence heads
