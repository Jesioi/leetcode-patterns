# Sliding Window

Core Pattern:
expand right pointer
shrink left pointer when window becomes invalid

Core Invariant:
window represents current valid / candidate range

Main Types:

## 1. Fixed Size Window

Use when window length is fixed.

Representative Problems:
- Permutation In String
- Sliding Window Maximum

Key Move:
right expands
if window size > k:
    remove left

## 2. Variable Window - Longest Valid

Use when asking for longest substring/subarray.

Representative Problems:
- Longest Substring Without Repeating Characters
- Longest Repeating Character Replacement

Key Move:
expand right
while invalid:
    shrink left
update max length

## 3. Variable Window - Minimum Valid

Use when asking for shortest/minimum window.

Representative Problems:
- Minimum Window Substring

Key Move:
expand right until valid
while valid:
    update answer
    shrink left

## 4. Sliding Window + Monotonic Deque

Use when needing max/min inside each window.

Representative Problems:
- Sliding Window Maximum

Key Insight:
deque stores useful candidates in decreasing order

Signals:
- substring
- subarray
- contiguous
- at most K
- minimum window
- fixed window size
- max/min in every window

Common Pitfalls:
- updating answer before window is valid
- shrinking with if when while is needed
- forgetting to remove left char/count
- confusing fixed-size window with variable-size window