# Heap / Priority Queue

Core Pattern:
Always process the smallest
or largest element first.

Core Insight:
A heap maintains the current
best candidate efficiently.

Instead of sorting repeatedly,
keep only the elements we need.

Core Components:

- PriorityQueue
- min heap
- max heap
- comparator

Recognition Signals:

- Top K
- Kth largest
- Kth smallest
- closest
- highest frequency
- continuously retrieve best element
- stream processing

Template Signal:

- top k frequent
- k closest points
- kth largest element
- merge k sorted lists
- task scheduler
- median from data stream

Key Questions:

What is the "best" element
I need right now?

Can a heap maintain it
more efficiently than sorting?

Common Heap Types:

Min Heap:

- smallest element on top
- useful for keeping K largest elements

Max Heap:

- largest element on top
- useful for repeatedly extracting maximum

Typical Complexity:

Build Heap:
O(n)

Insert:
O(log n)

Remove Top:
O(log n)

Peek:
O(1)

Common Bugs:

- using wrong heap direction
- forgetting custom comparator
- sorting when heap is sufficient
- keeping too many elements in heap
- confusing min heap vs max heap

Representative Problems:

- Top K Frequent Elements
- Kth Largest Element in an Array
- K Closest Points to Origin
- Merge K Sorted Lists
- Find Median from Data Stream

Mental Model:

Heap =
a constantly maintained leaderboard

Top element =
current best candidate

Every insertion updates
the leaderboard automatically.
