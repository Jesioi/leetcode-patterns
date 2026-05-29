# Contains Duplicate

Pattern:
hash set lookup

Brute Force:
nested loop compare every pair

Key Insight:
store previously seen values in HashSet

Core Idea:
if value already exists in set:
duplicate found

Complexity:
O(n)

Common Pitfalls:

- forgetting set.contains before add

Why This Matters:
foundation of hashmap/set problems
