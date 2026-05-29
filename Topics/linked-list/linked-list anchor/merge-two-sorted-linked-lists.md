# Merge Two Sorted Lists

## Pattern

Dummy Node + Merge Pointer

---

## Trigger

Use this pattern when:

- Merging two sorted linked lists
- Merging two sorted arrays
- Need ordered traversal from multiple sorted sources
- Need stable incremental construction

Typical keywords:

```text
sorted
merge
combine in order
smallest first
```

---

## Core Invariant

After each iteration:

- `dummy.next` = head of merged sorted list
- `tail` = last node of merged list
- `list1` and `list2` = remaining unprocessed nodes

The merged portion is always sorted.

---

## Pointer Flow

Each iteration:

```text
1. Compare list1.val and list2.val
2. Attach smaller node to tail.next
3. Move tail forward
4. Move chosen list pointer forward
```

After loop:

```text
Attach remaining nodes
```

---

## Iterative Solution

```java
public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
    ListNode dummy = new ListNode();
    ListNode tail = dummy;

    while (list1 != null && list2 != null) {
        if (list1.val < list2.val) {
            tail.next = list1;
            list1 = list1.next;
        } else {
            tail.next = list2;
            list2 = list2.next;
        }

        tail = tail.next;
    }

    tail.next = (list1 != null) ? list1 : list2;

    return dummy.next;
}
```

---

## Why Use Dummy Node?

Without dummy:

- first insertion becomes special case
- need manual head initialization
- more edge-case bugs

Dummy node stabilizes:

```text
head creation
tail movement
empty list handling
```

---

## Why Tail Pointer Matters

`tail` always points to:

```text
the last node of merged list
```

This allows:

```java
tail.next = smallerNode;
tail = tail.next;
```

to append nodes safely.

---

## Common Failure Reasons

### 1. Forgetting to move tail

Wrong:

```java
tail.next = list1;
```

without:

```java
tail = tail.next;
```

---

### 2. Forgetting remaining nodes

After loop, one list may still contain nodes.

Must attach:

```java
tail.next = list1 != null ? list1 : list2;
```

---

### 3. Returning tail instead of dummy.next

Wrong:

```java
return tail;
```

Correct:

```java
return dummy.next;
```

Because:

```text
tail = end of merged list
dummy.next = actual head
```

---

## Time Complexity

O(n + m)

---

## Space Complexity

O(1)

---

## Related Problems

### Same Merge Pattern

- Merge K Sorted Lists
- Sort List
- Reorder List
- Add Two Numbers

---

## Anchor Pattern

This is the foundational:

```text
merge two streams
```

pattern.

Many linked list medium/hard problems are variations of this idea.

---

## Recall Checklist

Before coding:

- [ ] create dummy
- [ ] create tail
- [ ] compare two nodes
- [ ] attach smaller node
- [ ] move tail
- [ ] attach remaining nodes
- [ ] return dummy.next

---

## Interview Goal

Target:

- recognize pattern within 5 seconds
- code within 5~8 minutes
- no pointer mistakes
- explain invariant while coding
