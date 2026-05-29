# Remove Nth Node From End of List

## Pattern

- Linked List
- Length Counting
- Delete Node by Previous Pointer

---

## Trigger

Use this pattern when:

- Need to delete the nth node from the end
- Need to convert “from end” into “from front”
- Need to remove a node in singly linked list

Typical keywords:

```text
remove nth from end
delete from end
linked list remove node
```

---

## Core Insight

Singly linked list can only move forward.

So instead of deleting directly from the end, we first get the length:

```text
removeIdx = len - n
```

This converts:

```text
nth node from end
```

into:

```text
index from front
```

---

## Core Invariant

To delete a linked list node, we usually stand at:

```text
previous node
```

Then update:

```java
prev.next = prev.next.next;
```

---

## Step-by-Step Logic

### Step 1 — Count Length

Traverse the list once:

```java
while (cur != null) {
    len++;
    cur = cur.next;
}
```

---

### Step 2 — Convert Index

```java
int removeIdx = len - n;
```

Example:

```text
head = [1,2,3,4,5], n = 2

len = 5
removeIdx = 5 - 2 = 3
```

Index:

```text
0  1  2  3  4
1  2  3  4  5
```

Delete index `3`, which is node `4`.

---

### Step 3 — Handle Removing Head

If:

```java
removeIdx == 0
```

it means delete the head.

So return:

```java
return head.next;
```

---

### Step 4 — Move to Previous Node

We need to stop at:

```text
removeIdx - 1
```

because deletion needs the previous node.

```java
for (int i = 0; i < removeIdx - 1; i++) {
    cur = cur.next;
}
```

---

### Step 5 — Delete Node

```java
cur.next = cur.next.next;
```

---

## Solution

```java
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
        int len = 0;
        ListNode cur = head;

        // count length
        while (cur != null) {
            len++;
            cur = cur.next;
        }

        int removeIdx = len - n;

        // remove head
        if (removeIdx == 0) {
            return head.next;
        }

        cur = head;

        // move to previous node
        for (int i = 0; i < removeIdx - 1; i++) {
            cur = cur.next;
        }

        // delete target node
        cur.next = cur.next.next;

        return head;
    }
}
```

---

## Why Move to Previous Node?

Because in linked list deletion:

```java
cur.next = cur.next.next;
```

means:

```text
delete cur.next
```

So `cur` must be the node before the target.

Example:

```text
1 -> 2 -> 3 -> 4 -> 5
          ^
        delete 3
```

We stand at node `2`:

```text
1 -> 2 ------> 4 -> 5
```

---

## Common Failure Reasons

### 1. Confusing removeIdx with previous index

```text
removeIdx = node to delete
removeIdx - 1 = previous node
```

---

### 2. Forgetting head case

If deleting head, there is no previous node.

Need:

```java
return head.next;
```

---

### 3. For loop goes one step too far

Correct:

```java
i < removeIdx - 1
```

Wrong:

```java
i <= removeIdx - 1
```

---

### 4. Thinking cur is deleted

This line:

```java
cur.next = cur.next.next;
```

does not delete `cur`.

It deletes:

```text
cur.next
```

---

## Time Complexity

```text
O(n)
```

Two passes through the linked list.

---

## Space Complexity

```text
O(1)
```

---

## Related Problems

- Delete Node in a Linked List
- Middle of the Linked List
- Linked List Cycle
- Reorder List
- Merge Two Sorted Lists

---

## Anchor Pattern

This is a basic linked list deletion pattern:

```text
find previous node
+
skip target node
```

Core line:

```java
prev.next = prev.next.next;
```

---

## Recall Checklist

Before coding:

- [ ] count length
- [ ] calculate `removeIdx = len - n`
- [ ] handle `removeIdx == 0`
- [ ] move to `removeIdx - 1`
- [ ] delete with `cur.next = cur.next.next`

---

## Interview Goal

Target:

- recognize index conversion within 10 seconds
- explain why previous node is needed
- code without off-by-one bugs
- finish within 10~15 minutes
