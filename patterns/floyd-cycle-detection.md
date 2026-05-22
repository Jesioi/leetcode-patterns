# Floyd Cycle Detection

## Core Idea

Use slow and fast pointers to detect cycles.

- slow moves 1 step
- fast moves 2 steps

If they meet:
there is a cycle.

---

## Related Problems

- Linked List Cycle

  - Detect whether cycle exists.

- Linked List Cycle II

  - Find cycle entrance.

- Find Duplicate Number

  - Treat array index as linked list next pointer.

  ```java
  next = nums[index]
  ```

- Happy Number

- Circular array loop

---

Phase 1:
slow 1 step
fast 2 step

if meet:
reset one pointer to head

Phase 2:
both move 1 step

next meeting point = cycle entrance

---

## Phase 1: Detect Meeting Point

```java
while (fast != null && fast.next != null) {
    slow = slow.next;
    fast = fast.next.next;

    if (slow == fast) {
        // cycle exists
    }
}
```

---

## Phase 2: Find Cycle Entrance

After meeting:

- reset one pointer to head
- move both 1 step each time

Next meeting point = cycle entrance.

```java
slow = head;

while (slow != fast) {
    slow = slow.next;
    fast = fast.next;
}
```

return slow;

````

---

## Why It Works

Distance from:

- head -> cycle entrance

equals

- meeting point -> cycle entrance (inside cycle)

---

## Common Pitfalls

### 1. Forgetting null check

Wrong:

```java
while (fast != null)
````

Correct:

```java
while (fast != null && fast.next != null)
```

---

### 2. Returning meeting point directly

Meeting point is NOT necessarily the entrance.

Need phase 2.

---

## Pattern Recognition

Usually appears when:

- repeated traversal
- cycle structure
- duplicate creates loop
- O(1) space required

---

## Anchor Insight

Cycle entrance detection:

1. slow/fast meet
2. reset one pointer to head
3. move both 1 step
4. next meeting point = entrance
