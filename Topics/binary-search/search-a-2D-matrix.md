# Search a 2D Matrix

## Pattern

Binary Search (Two-Phase) — Row Boundary Search + Column Exact Match

## Trigger

- Matrix where each row is sorted AND the first element of each row is greater than the last element of the previous row
- Matrix behaves like a globally sorted array — treat it as one

## Core Invariant

Phase 1: Find the last row whose first element is `<= target` (boundary search on rows).
Phase 2: Exact match binary search within that row.

After Phase 1, `right` lands on the candidate row. If `right < 0`, target is impossible.

## Pointer Flow

```
Phase 1 — boundary search on rows:
  left = 0, right = numRows - 1
  while left <= right:
      mid = left + (right - left) / 2
      if matrix[mid][0] == target  → return true
      if matrix[mid][0] > target   → right = mid - 1
      else                         → left = mid + 1
  targetRow = right

Phase 2 — exact match in targetRow:
  left = 0, right = numCols - 1
  while left <= right:
      mid = left + (right - left) / 2
      if matrix[targetRow][mid] == target  → return true
      if matrix[targetRow][mid] > target   → right = mid - 1
      else                                 → left = mid + 1

return false
```

```java
public boolean searchMatrix(int[][] matrix, int target) {
    int rows = matrix.length, cols = matrix[0].length;
    int left = 0, right = rows - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (matrix[mid][0] == target) return true;
        if (matrix[mid][0] > target)  right = mid - 1;
        else                          left = mid + 1;
    }

    int targetRow = right;
    if (targetRow < 0) return false;

    left = 0; right = cols - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (matrix[targetRow][mid] == target) return true;
        if (matrix[targetRow][mid] > target)  right = mid - 1;
        else                                  left = mid + 1;
    }

    return false;
}
```

## Common Failure Reasons

- **Using `left` instead of `right` as `targetRow`**: after boundary search, `right` points to the last valid row; `left` has overshot
- **Not checking `targetRow < 0`**: if target is smaller than all first elements, `right` ends at -1
- **Treating Phase 1 as exact match**: it's a boundary search — the row's first element won't equal target in most cases

## Related Problems

- Binary Search — exact match anchor pattern
- Koko Eating Bananas — binary search on a different kind of answer space
- Search in Rotated Sorted Array — binary search with a broken monotonic property

## Complexity

Time: O(log m + log n) — two independent binary searches
Space: O(1)

## Interview Goal

Clearly articulate the two-phase split before coding.
Know that `right` (not `left`) is the result of a boundary search.
