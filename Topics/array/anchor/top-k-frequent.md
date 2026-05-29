# Top K Frequent Elements

Pattern:
frequency counting + heap/bucket sort

Brute Force:
sort by frequency

Key Insight:
count first
then retrieve largest frequencies

Core Structure:
HashMap + Heap

Signals:

- top k
- most frequent
- ranking

Complexity:
O(n log k)

Common Pitfalls:

- sorting entire array unnecessarily

Why This Matters:
frequency + heap combination pattern
