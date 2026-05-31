# Binary Search on Answer

Core Pattern:
Binary search over the answer space,
not the array index.

Core Insight:
If an answer is feasible,
then all easier answers are also feasible.

This creates a monotonic condition.

Core Components:

- left boundary
- right boundary
- mid as candidate answer
- feasibility check
- shrink search space

Recognition Signals:

- minimum possible maximum
- maximum possible minimum
- smallest valid value
- largest valid value
- minimize capacity / speed / time
- answer range is numeric
- can check if a candidate works

Template Signal:

- Koko Eating Bananas
- Capacity To Ship Packages
- Split Array Largest Sum
- Minimize Maximum
- Minimum Days

Key Question:

Can this candidate answer work?

If yes:
try a smaller/larger answer
depending on the goal

If no:
move toward the feasible side

Common Workflow:

1. Define search range
2. Write `can(mid)` function
3. Binary search for boundary
4. Return best feasible answer

Common Bugs:

- searching index instead of answer
- wrong left / right bounds
- unclear feasible condition
- infinite loop from boundary update
- off-by-one in return value

Representative Problems:

- Koko Eating Bananas
- Capacity To Ship Packages Within D Days
- Split Array Largest Sum
- Minimize Maximum of Array
- Minimum Number of Days to Make m Bouquets

Mental Model:

You are not looking for an element.

You are looking for the smallest or largest
answer that satisfies a condition.

Typical Template:

```java
int left = minPossible;
int right = maxPossible;

while (left < right) {
    int mid = left + (right - left) / 2;

    if (can(mid)) {
        right = mid;
    } else {
        left = mid + 1;
    }
}

return left;
```

Feasibility Function:

```java
private boolean can(int mid) {
    // return true if mid is enough / valid / feasible
}
```

Core Invariant:

`left` and `right` always contain
the final answer range.

When `can(mid)` is true,
we keep mid as a possible answer.
