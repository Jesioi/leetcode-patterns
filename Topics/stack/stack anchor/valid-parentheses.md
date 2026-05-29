# Problem: Valid Parentheses

Anchor Pattern:
Stack matching

## Core Invariant:

stack stores unmatched opening brackets

## Failure Pattern:

mixed queue operation with stack invariant
used offerLast + pop, causing FIFO behavior instead of LIFO

## Fix:

Deque as stack must use same-end operations:
push/pop
or offerLast/pollLast

## Status:

minor bug
