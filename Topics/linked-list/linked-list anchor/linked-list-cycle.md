# Linked List Cycle

## Pattern

Fast & Slow Pointer (Floyd Cycle Detection)

---

## Trigger

Use when:

- detecting cycle
- finding middle
- circular traversal
- O(1) space requirement

---

## Core Invariant

After each iteration:

- slow moves 1 step
- fast moves 2 steps

If cycle exists:

- fast eventually catches slow

---

## Intuition

Like running on a track:

- fast runner laps slow runner
- eventually they meet inside cycle

---

## Pointer Flow

```text
slow = slow.next
fast = fast.next.next
```

If:

```text
slow == fast
```

cycle exists.

---

## Solution

```java
public boolean hasCycle(ListNode head) {
    ListNode slow = head;
    ListNode fast = head;

    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;

        if (slow == fast) {
            return true;
        }
    }

    return false;
}
```

---

## Why Check fast.next != null?

Because:

```java
fast = fast.next.next;
```

requires:

- fast exists
- fast.next exists

Otherwise:

```text
NullPointerException
```

---

## Common Failure Reasons

### 1. Using fast != null only

Wrong:

```java
while (fast != null)
```

because:

```java
fast.next.next
```

may crash.

只要后面要用 fast.next.next，while 里必须先检查 fast != null && fast.next != null。

---

### 2. Comparing values instead of nodes

Wrong:

```java
slow.val == fast.val
```

Correct:

```java
slow == fast
```

Need reference equality.

---

## Time Complexity

O(n)

---

## Space Complexity

O(1)

---

## Related Problems

- Find Duplicate Number
- Middle of Linked List
- Linked List Cycle II
- Happy Number

---

## Anchor Pattern

This is the foundational:

```text
fast slow pointer
```

pattern.

---

## Recall Checklist

- [ ] slow moves 1
- [ ] fast moves 2
- [ ] check fast and fast.next
- [ ] compare node references
- [ ] return true if meet

---

## Interview Goal

Target:

- recognize within 5 seconds
- code within 5 minutes
- explain WHY meeting happens
