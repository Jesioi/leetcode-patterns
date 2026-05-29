# Daily Temperatures

## Pattern

Monotonic Decreasing Stack / Next Greater Element

---

## Trigger

Use this pattern when:

- Need the **next greater** (or next smaller) element for each index
- Result for each element depends on a future element
- Brute force would be a nested scan: O(n²)

---

## Core Invariant

The stack holds indices of elements **waiting for their next greater element**.
Stack values (temperatures) are always monotonically decreasing top → bottom.

When a new element resolves a previous one, pop and record the answer.

```text
stack (indices): [i1, i2, i3]  where T[i1] >= T[i2] >= T[i3]
new element T[j] > T[i3]  →  pop i3, answer[i3] = j - i3
```

---

## Pointer Flow

```
for each index j:
    while stack not empty AND T[j] > T[stack.top()]:
        i = stack.pop()
        answer[i] = j - i
    stack.push(j)          ← always push AFTER the while loop

remaining stack entries: never found a warmer day → answer stays 0
```

```java
public int[] dailyTemperatures(int[] temperatures) {
    int n = temperatures.length;
    int[] answer = new int[n];
    Deque<Integer> stack = new ArrayDeque<>();

    for (int j = 0; j < n; j++) {
        while (!stack.isEmpty() && temperatures[j] > temperatures[stack.peek()]) {
            int i = stack.pop();
            answer[i] = j - i;
        }
        stack.push(j);
    }

    return answer;
}
```

---

## Common Failure Reasons

- **Pushing before the while loop**: push must come after, or you'll resolve an element against itself
- **Storing values instead of indices**: you need the index to compute the distance `j - i`
- **Using >= instead of >**: strictly greater, not greater-or-equal

---

## Related Problems

- Largest Rectangle in Histogram — monotonic increasing stack, same pop-and-calculate structure
- Next Greater Element I / II — same pattern, with circular array variant
- Trapping Rain Water — two-pointer variant of the same span-resolution idea

---

## Complexity

Time: O(n) — each element is pushed and popped at most once
Space: O(n) — stack

---

## Interview Goal

Explain why O(n): each element enters and leaves the stack exactly once.
Code without hesitation: while loop pops, then push outside.
