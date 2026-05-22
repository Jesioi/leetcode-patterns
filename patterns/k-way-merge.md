# K-Way Merge Using Min Heap

## Core Idea

Use a min heap to always get:

the current smallest element
among all sorted sources.

After removing the smallest element:

push its next element back into the heap.

---

## Invariant

PriorityQueue always stores:

the current smallest unprocessed node
from each list/source.

---

## Template

```java
PriorityQueue<ListNode> pq =
    new PriorityQueue<>(
        (a, b) -> Integer.compare(a.val, b.val)
    );

for (ListNode node : lists) {
    if (node != null) {
        pq.offer(node);
    }
}

while (!pq.isEmpty()) {
    ListNode min = pq.poll();

    // use min node

    if (min.next != null) {
        pq.offer(min.next);
    }
}
```

---

## Why It Works

Each list is already sorted.

So after removing one node:

only its next node
can become the next candidate.

Heap size never exceeds:

```text
k
```

where:

```text
k = number of lists
```

---

## Complexity

Let:

```text
N = total number of nodes
k = number of lists
```

### Time

```text
O(N log k)
```

Each node:

- enters heap once
- leaves heap once

Heap operations cost:

```text
log k
```

---

### Space

```text
O(k)
```

for the heap.

---

## Common Pitfalls

### 1. Pushing null into heap

Wrong:

```java
pq.offer(node);
```

Correct:

```java
if (node != null)
```

---

### 2. Using push/pop in Java

PriorityQueue uses:

```java
offer()
poll()
```

---

### 3. Comparator overflow

Avoid:

```java
(a, b) -> a.val - b.val
```

Prefer:

```java
Integer.compare(a.val, b.val)
```

---

## Recognition Signals

Usually appears when:

- multiple sorted streams
- merge k sorted structures
- repeatedly need global minimum
- "smallest among many sorted sources"

---

## Related Problems

### Merge K Sorted Lists

Classic linked list version.

### Kth Smallest Element

Heap stores current smallest candidates.

### Top K Frequent Elements

Heap maintains top candidates.

### Merge Sorted Streams

Industrial streaming version.

---

## Anchor Insight

Heap stores:

the current minimum candidate
from each sorted source.
