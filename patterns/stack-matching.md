# Stack Matching

Core Pattern:
stack stores unmatched opening tokens

Invariant:
top of stack must match current closing token

Signals:

- parentheses
- brackets
- nested structure
- valid expression

Representative Problems:

- Valid Parentheses

Common Pitfalls:

- using queue behavior by accident
- forgetting empty stack check before pop
