# Fast Slow Pointers

Core Pattern:
slow moves 1 step
fast moves 2 steps

Key Insight:
different speeds reveal structure

Common Uses:

- cycle detection
- middle node
- linked list split

Invariant:
distance between pointers changes predictably

Template:

while (fast != null && fast.next != null) {
slow = slow.next;
fast = fast.next.next;
}

Signals:

- cycle
- middle
- repeated structure

Representative Problems:

- Linked List Cycle
- Find Middle of Linked List
- Find The Duplicate Number
