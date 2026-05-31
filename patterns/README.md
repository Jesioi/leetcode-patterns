# Pattern Library

Goal:

Identify patterns in 30 seconds
before writing code.

---

# Number Topic Tree

- 000: DFS / Recursion
- 100: Array Patterns
- 200: Ordering / Priority Patterns
- 300: Binary Search Patterns
- 400: Graph Patterns
- 500: Specialized Data Structures
- 600: Dynamic Programming

# Numbering System

## 000 Series — DFS / Recursion

Core Idea:

Explore state space recursively.

Patterns:

- 000 DFS Recursion
- 002 Backtracking
- 003 Return Value DFS
- 004 Constraint Propagation DFS

Typical Domains:

- Tree
- Graph
- Backtracking

Representative Problems:

- Maximum Depth of Binary Tree
- Diameter of Binary Tree
- Subsets
- Permutations
- Validate BST

---

## 100 Series — Array Patterns

Core Idea:

Process arrays efficiently
without extra nested loops.

Patterns:

- 100 Sliding Window
- 101 Two Pointers Opposite
- 102 Fast Slow Pointers
- 103 Prefix Sum
- 104 HashMap Frequency

Representative Problems:

- Longest Substring Without Repeating Characters
- Two Sum
- Product Except Self
- Linked List Cycle
- Subarray Sum Equals K

---

## 200 Series — Ordering / Priority Patterns

Core Idea:

Maintain order while processing.

Patterns:

- 200 Stack Matching
- 201 Stack Simulation
- 202 Monotonic Stack
- 203 K-Way Merge
- 204 Heap / Priority Queue
- 205 Intervals

Representative Problems:

- Valid Parentheses
- Daily Temperatures
- Largest Rectangle in Histogram
- Merge K Sorted Lists
- Top K Frequent Elements
- Merge Intervals

---

## 300 Series — Binary Search Patterns

Core Idea:

Exploit monotonicity.

Patterns:

- 300 Binary Search
- 301 Floyd Cycle Detection
- 302 Search On Answer

Representative Problems:

- Binary Search
- Search 2D Matrix
- Find Duplicate Number
- Koko Eating Bananas

---

## 400 Series — Graph Patterns

Core Idea:

Process relationships between nodes.

Patterns:

- 400 Graph Grid Traversal
- 401 Multi Source BFS
- 402 Topological Sort
- 403 Union Find
- 404 Graph Cloning
- 405 Shortest Path BFS

Representative Problems:

- Number of Islands
- Rotten Oranges
- Course Schedule
- Redundant Connection
- Clone Graph
- Word Ladder

---

## 500 Series — Specialized Data Structures

Patterns:

- 500 Trie

Representative Problems:

- Implement Trie
- Word Search II

---

## 600 Series — Dynamic Programming

Core Idea:

Reuse previously solved subproblems.

Patterns:

- 600 1D DP
- 601 2D DP
- 602 Knapsack

Representative Problems:

- Climbing Stairs
- House Robber
- Coin Change
- Longest Common Subsequence

---

# Pattern Selection Guide

Question asks:

Shortest path?
→ 405 Shortest Path BFS

Dependency ordering?
→ 402 Topological Sort

Cycle in undirected graph?
→ 403 Union Find

Top K?
→ 204 Heap

Overlap ranges?
→ 205 Intervals

Subset / Combination?
→ 002 Backtracking

Tree information flows upward?
→ 003 Return Value DFS

Tree constraints passed downward?
→ 004 Constraint Propagation

Monotonic condition?
→ 300 / 302 Binary Search
