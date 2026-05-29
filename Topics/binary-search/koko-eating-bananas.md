# Koko Eating Bananas

## Pattern

Binary Search on Answer Space

## Trigger

- "Find the **minimum** X such that a condition holds"
- The feasibility function `canDo(X)` is **monotonic**: once true, always true for larger X
- Brute force is trying every candidate value from min to max

## Core Invariant

Search space is `[1, max(piles)]`.
`canFinish(k)` is monotonically true once `k` is large enough.
Binary search on `k` to find the leftmost `k` where `canFinish(k)` is true.

## Pointer Flow

```
left = 1, right = max(piles)

while left <= right:
    mid = left + (right - left) / 2

    if canFinish(mid):
        result = mid
        right = mid - 1   (try smaller)
    else:
        left = mid + 1    (too slow, try larger)

return result
```

```java
public int minEatingSpeed(int[] piles, int h) {
    int left = 1;
    int right = 0;
    for (int p : piles) right = Math.max(right, p);

    int result = right;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (canFinish(piles, mid, h)) {
            result = mid;
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }
    return result;
}

private boolean canFinish(int[] piles, int k, int h) {
    long hours = 0;
    for (int pile : piles) {
        hours += (pile + k - 1) / k;  // ceiling division
    }
    return hours <= h;
}
```

## Common Failure Reasons

- **Wrong search space**: searching pile indices, not speed values — `left = 1`, `right = max(piles)`
- **Integer overflow in `hours`**: use `long`, not `int`
- **Wrong ceiling division**: `(pile + k - 1) / k`, not `pile / k`
- **Not saving `result`**: must record the last valid `mid` before shrinking right

## Related Problems

- Binary Search — exact match, the anchor pattern
- Capacity to Ship Packages Within D Days — same binary search on answer template
- Find Minimum in Rotated Sorted Array — boundary search, different variant

## Complexity

Time: O(n log m) — n piles, m = max pile size
Space: O(1)

## Interview Goal

Recognize "minimize X subject to a feasibility condition" as binary search on the answer.
Write `canFinish` cleanly before writing the binary search loop.
