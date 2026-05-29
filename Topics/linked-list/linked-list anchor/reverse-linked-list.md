# Reverse Linked List

## Pattern

Reverse Pointer Manipulation

---

## Trigger

Use this pattern when:

- Need to reverse linked list direction
- Need to process linked list from tail to head
- Need partial reverse
- Need k-group reverse
- Need reorder / palindrome operations

---

## Core Invariant

After each iteration:

- `prev` = head of reversed part
- `curr` = head of remaining unprocessed part

The list is always split into:

```text
reversed part <- prev
unprocessed part -> curr
```
