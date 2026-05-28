# Binary Search

Core Pattern:
use mid to eliminate half of the search space

Core Invariant:
the answer is always inside the current search range

Key Insight:
binary search is not only for sorted arrays.
It works whenever there is a monotonic condition.

Main Types:

## 1. Exact Match Binary Search

Use when searching for a target in a sorted array.

Template:

while (left <= right) {
int mid = left + (right - left) / 2;

    if (nums[mid] == target) {
        return mid;
    } else if (nums[mid] < target) {
        left = mid + 1;
    } else {
        right = mid - 1;
    }

}

Representative Problems:

- Binary Search
- Search a 2D Matrix

## 2. Boundary Search

Use when finding minimum / maximum valid position.

Key Move:
when mid is valid,
record answer and continue searching for better answer

Signals:

- first true
- last false
- lower bound
- upper bound

## 3. Binary Search on Answer

Use when the array itself is not sorted,
but the answer space is monotonic.

Key Question:
"if mid works, can larger/smaller values also work?"

Representative Problems:

- Koko Eating Bananas
- Capacity To Ship Packages Within D Days

## 4. Rotated Sorted Array

Key Insight:
one side is always sorted

Decision:
identify sorted half
then decide whether target is inside that half

Representative Problems:

- Search In Rotated Sorted Array
- Find Minimum In Rotated Sorted Array

Signals:

- sorted array
- monotonic condition
- minimum feasible
- maximum feasible
- rotated sorted array
- search space

Common Pitfalls:

- infinite loop from not moving left/right
- mid overflow
- using left < right vs left <= right incorrectly
- forgetting to preserve possible answer
- confusing exact search with boundary search

Complexity:
O(log n)

Why This Works:
each decision removes half of the remaining candidates
without discarding the true answer
