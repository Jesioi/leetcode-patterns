# Two Sum

Pattern:
hashmap complement lookup

Brute Force:
try every pair

Key Insight:
for current number x
search target - x in hashmap

Core Formula:
target - nums[i]

Invariant:
map stores previously seen numbers

Complexity:
O(n)

Common Pitfalls:

- inserting before checking
- duplicate values

Why This Matters:
foundation of complement-search problems
