# Binary Search

## Pattern

Binary Search (Exact Match)

## Trigger

- Array or search space is **sorted** (or has a monotonic property)
- You need to find a target or a boundary in O(log n)
- Brute force would be O(n) linear scan

## Core Invariant

The answer is always inside `[left, right]`.
Each iteration, one half is eliminated because the target cannot be there.

`mid = left + (right - left) / 2` — avoids integer overflow.

## Pointer Flow

```
left = 0, right = n - 1

while left <= right:
    mid = left + (right - left) / 2

    if nums[mid] == target  → return mid
    if nums[mid] < target   → left = mid + 1   (discard left half)
    if nums[mid] > target   → right = mid - 1  (discard right half)

return -1  (not found)
```

```java
public int search(int[] nums, int target) {
    int left = 0;
    int right = nums.length - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (nums[mid] == target) return mid;
        if (nums[mid] < target)  left = mid + 1;
        else                     right = mid - 1;
    }

    return -1;
}
```

## Common Failure Reasons

- **Off-by-one on loop condition**: `left <= right` for exact match; `left < right` for boundary search
- **Not using `left + (right - left) / 2`**: `(left + right) / 2` overflows for large indices
- **Wrong shrink direction**: if `nums[mid] < target`, eliminate left half → `left = mid + 1`

## Related Problems

- Koko Eating Bananas — binary search on the answer space, not an index
- Search a 2D Matrix — two-phase binary search on a virtually flattened sorted matrix
- Find Minimum in Rotated Sorted Array — boundary search variant

## Complexity

Time: O(log n)
Space: O(1)

## Interview Goal

Write both the exact-match and boundary-search variants from memory.
Know immediately which variant a problem requires from its phrasing.
