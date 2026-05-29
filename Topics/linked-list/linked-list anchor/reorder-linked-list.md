# Reorder List

## Pattern

- Fast Slow Pointer
- Reverse Linked List
- Merge Two Lists

---

## Trigger

Use this pattern when:

- Need to reorder from both ends
- Need alternating front/back merge
- Need access to tail nodes in singly linked list
- Need split + reverse + merge workflow

Typical keywords:

```text
L0 → Ln → L1 → Ln-1
reorder
alternate front/back
```

---

## Core Insight

Singly linked list cannot efficiently access tail nodes.

Instead of repeatedly finding tail:

```text
O(n²)
```

we:

```text
1. find middle
2. reverse second half
3. merge alternating
```

This converts:

```text
tail access problem
```

into:

```text
head access problem
```

---

## Core Invariant

After splitting:

```text
first half -> normal order
second half -> reversed order
```

During merge:

```text
nodes alternate between:
first half
second half
```

---

## Step-by-Step Logic

### Step 1 — Find Middle

Use fast/slow pointer.

```text
slow = midpoint
```

---

### Step 2 — Reverse Second Half

Convert:

```text
1 -> 2 -> 3 -> 4 -> 5
```

into:

```text
1 -> 2 -> 3

5 -> 4
```

Now tail nodes become easy to access.

---

### Step 3 — Merge Alternating

Merge:

```text
1 -> 2 -> 3
5 -> 4
```

into:

```text
1 -> 5 -> 2 -> 4 -> 3
```

---

## Solution

```java
public void reorderList(ListNode head) {
    if (head == null || head.next == null) {
        return;
    }

    // find middle
    ListNode slow = head;
    ListNode fast = head.next;

    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }

    // reverse second half
    ListNode second = slow.next;
    slow.next = null;

    ListNode prev = null;

    while (second != null) {
        ListNode temp = second.next;
        second.next = prev;
        prev = second;
        second = temp;
    }

    // merge two halves
    ListNode first = head;
    second = prev;

    while (second != null) {
        ListNode temp1 = first.next;
        ListNode temp2 = second.next;

        first.next = second;
        second.next = temp1;

        first = temp1;
        second = temp2;
    }
}
```

---

## Why Reverse Second Half?

Without reverse:

```text
1 -> 2 -> 3 -> 4 -> 5
```

we cannot efficiently access:

```text
5
then 4
then 3
```

because singly linked list has no backward traversal.

Reverse converts:

```text
5 -> 4 -> 3
```

into a forward traversal problem.

---

## Common Failure Reasons

### 1. Forgetting to cut the list

Missing:

```java
slow.next = null;
```

can create cycle issues.

---

### 2. Pointer overwrite during merge

Need temporary variables:

```java
temp1
temp2
```

before reconnecting pointers.

---

### 3. Wrong fast initialization

Using:

```java
fast = head
```

vs

```java
fast = head.next
```

changes midpoint behavior.

---

### 4. Forgetting reverse invariant

During reverse:

```text
prev = reversed part
second = unprocessed part
```

---

## Time Complexity

O(n)

---

## Space Complexity

O(1)

---

## Related Problems

- Reverse Linked List
- Reverse Linked List II
- Reverse Nodes In K Group
- Palindrome Linked List
- Merge Two Sorted Lists

---

## Anchor Pattern

This is a major linked list composite pattern:

```text
fast slow
+
reverse
+
merge
```

Many linked list hard problems are combinations of these three patterns.

---

## Recall Checklist

Before coding:

- [ ] find middle
- [ ] cut list
- [ ] reverse second half
- [ ] merge alternating
- [ ] protect pointers with temp variables

---

## Interview Goal

Target:

- recognize pattern within 10 seconds
- explain WHY reverse is needed
- independently code within 20~25 minutes
- avoid merge pointer bugs
