# Monotonic Stack

Core Pattern:
maintain increasing/decreasing order

Key Insight:
stack keeps only useful candidates

Core Invariant:
once an element loses the ability
to become a future answer,
it is permanently removed

Common Types:

- increasing stack
- decreasing stack

Template:

while (!stack.isEmpty() &&
stack.peek() < current) {
stack.pop();
}

Common Variants:

## Next Greater Element

Maintain decreasing stack.

When current element is larger:
pop smaller elements.

## Next Smaller Element

Maintain increasing stack.

When current element is smaller:
pop larger elements.

## Histogram Problems

Stack stores indices.

Height expansion determined by:
current index - previous smaller index

Signals:

- next greater element
- nearest larger/smaller
- histogram
- daily temperatures
- range expansion
- monotonic property

Representative Problems:

- Daily Temperatures
- Largest Rectangle in Histogram
- Next Greater Element
- Car Fleet

Common Pitfalls:

- forgetting to store index instead of value
- not processing remaining stack
- confusing increasing vs decreasing stack
- incorrect width calculation in histogram problems

Complexity:

Each element is pushed and popped at most once.

Time:
O(n)

Why This Works:

Elements removed from stack
can never become a better answer later.
So every element is processed only once.
