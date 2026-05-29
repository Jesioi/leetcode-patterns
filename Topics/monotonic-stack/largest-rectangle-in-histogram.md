# Largest Rectangle in Histogram

## Pattern

Monotonic Increasing Stack / Span Calculation

---

## Trigger

Use this pattern when:

- Need the **maximum area/span** where boundaries are set by smaller elements
- Each element's contribution depends on how far left and right it can extend
- A smaller element on the right terminates previous taller elements

---

## Core Invariant

The stack holds `[startIndex, height]` pairs, always monotonically increasing by height.

When a shorter bar arrives, all taller bars on the stack can no longer extend right.
Pop them immediately and calculate their max rectangle.

The popped bar's `startIndex` becomes the new bar's left boundary — the current height can inherit the space of all taller bars it absorbs.

```text
stack (increasing): [ [s1,h1], [s2,h2], [s3,h3] ]  h1 <= h2 <= h3

new bar height h < h3:
  pop [s3, h3]  → area = h3 * (i - s3)
  new bar inherits s3 as its left boundary
```

---

## Pointer Flow

```
for each index i:
    start = i
    while stack not empty AND stack.top().height > heights[i]:
        [idx, h] = stack.pop()
        area = h * (i - idx)
        update maxArea
        start = idx          ← inherit the left boundary

    stack.push([start, heights[i]])

after loop — remaining bars extend to the end:
    for [idx, h] in stack:
        area = h * (n - idx)
        update maxArea
```

```java
public int largestRectangleArea(int[] heights) {
    int maxArea = 0;
    Deque<int[]> stack = new ArrayDeque<>();

    for (int i = 0; i < heights.length; i++) {
        int start = i;
        while (!stack.isEmpty() && stack.peek()[1] > heights[i]) {
            int[] top = stack.pop();
            maxArea = Math.max(maxArea, top[1] * (i - top[0]));
            start = top[0];
        }
        stack.push(new int[]{start, heights[i]});
    }

    for (int[] pair : stack) {
        maxArea = Math.max(maxArea, pair[1] * (heights.length - pair[0]));
    }

    return maxArea;
}
```

---

## Common Failure Reasons

- **Forgetting the final stack traversal**: bars that never found a smaller right boundary still contribute
- **Not inheriting `start`**: the current bar can extend left through all taller bars it absorbs
- **Width formula wrong**: width is `i - poppedIndex`, not `i - i+1` or `stack.size()`

---

## Related Problems

- Daily Temperatures — monotonic decreasing stack, same pop-and-record structure
- Trapping Rain Water — area-between-bars variant
- Maximal Rectangle — apply this pattern row by row on a 2D grid

---

## Complexity

Time: O(n) — each bar is pushed and popped at most once
Space: O(n) — stack

---

## Interview Goal

Explain the `start` inheritance clearly before coding — it's the non-obvious step.
Nail both the inner loop and the final stack drain without prompting.
