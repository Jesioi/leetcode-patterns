# Linked List Recursion — Core Anchors

## Goal

Linked List recursion 不需要刷很多题。

真正核心的是掌握三种 recursive pointer transformation：

1. Reverse Family
2. Merge Family
3. Chunk / Block Family

所有 recursion linked list 题基本都从这三类变形。

---

# Anchor 1 — Reverse List

## Pattern

```java
public ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) {
        return head;
    }

    ListNode newHead = reverseList(head.next);

    head.next.next = head;
    head.next = null;

    return newHead;
}
```

## Core Intuition

递归返回时，后面的链表已经被翻转好了。

当前 node 只需要做一件事：

```text
让 head.next 指回 head
```

也就是：

```java
head.next.next = head;
```

## Example

Original:

```text
1 -> 2 -> 3 -> null
```

当递归返回到 `2` 时：

```text
3 -> 2
```

当递归返回到 `1` 时：

```text
3 -> 2 -> 1
```

## Key Line

```java
head.next.next = head;
```

Meaning:

```text
原本 head -> next
现在变成 next -> head
```

## Common Pitfall

一定要写：

```java
head.next = null;
```

否则会形成 cycle。

例如：

```text
1 -> 2
2 -> 1
```

如果不把 `1.next` 断开，就会无限循环。

## Related Problems

- Reverse Linked List
- Reverse Between
- Reverse Nodes in K Group
- Palindrome Linked List recursive version
- Reorder List recursive version

---

# Anchor 2 — Merge Two Sorted Lists

## Pattern

```java
public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
    if (l1 == null) return l2;
    if (l2 == null) return l1;

    if (l1.val < l2.val) {
        l1.next = mergeTwoLists(l1.next, l2);
        return l1;
    } else {
        l2.next = mergeTwoLists(l1, l2.next);
        return l2;
    }
}
```

## Core Intuition

Recursive function 帮我处理剩余链表。

当前 node 只负责：

1. 选谁当当前 head
2. 把当前 head.next 接到 recursive result
3. return 当前 head

## Example

```text
l1: 1 -> 3 -> 5
l2: 2 -> 4 -> 6
```

第一步：

```text
1 比 2 小
所以 1 是当前 head
```

然后：

```java
1.next = merge(3 -> 5, 2 -> 4 -> 6)
```

递归会帮你处理后面的 sorted merge。

## Core Mental Model

```text
当前节点接住 recursion 返回值
```

## Key Line

```java
l1.next = mergeTwoLists(l1.next, l2);
```

Meaning:

```text
我已经决定 l1 是当前节点
剩下的 merge 交给 recursion
然后把结果接到 l1.next
```

## Common Pitfall

不要只写：

```java
mergeTwoLists(l1.next, l2);
```

必须接住返回值：

```java
l1.next = mergeTwoLists(l1.next, l2);
```

因为 recursion 返回的是已经 merge 好的剩余链表 head。

## Related Problems

- Merge Two Sorted Lists
- Merge K Sorted Lists
- Sorted Insert
- Recursive list building problems

---

# Anchor 3 — Swap Nodes in Pairs / Chunk Processing

## Pattern

```java
public ListNode swapPairs(ListNode head) {
    if (head == null || head.next == null) {
        return head;
    }

    ListNode nextPair = head.next.next;
    ListNode newHead = head.next;

    newHead.next = head;
    head.next = swapPairs(nextPair);

    return newHead;
}
```

## Core Intuition

先处理当前 block，剩下交给 recursion。

对于 swap pairs：

```text
当前 block = 两个 node
```

例如：

```text
1 -> 2 -> 3 -> 4
```

先处理：

```text
2 -> 1
```

然后：

```java
1.next = swapPairs(3 -> 4)
```

## Example

Original:

```text
1 -> 2 -> 3 -> 4 -> null
```

处理第一组：

```text
2 -> 1
```

递归处理剩余：

```text
swapPairs(3 -> 4)
```

返回：

```text
4 -> 3
```

最终：

```text
2 -> 1 -> 4 -> 3 -> null
```

## Core Mental Model

```text
局部处理 + recurse 剩余部分
```

## Key Lines

```java
ListNode nextPair = head.next.next;
ListNode newHead = head.next;

newHead.next = head;
head.next = swapPairs(nextPair);
```

Meaning:

```text
newHead 是当前 pair 的第二个节点
让第二个节点指向第一个节点
再让第一个节点接住后面递归处理好的链表
```

## Common Pitfall

一定要先保存：

```java
ListNode nextPair = head.next.next;
```

否则你改指针后可能丢失后面的链表。

## Related Problems

- Swap Nodes in Pairs
- Reverse Nodes in K Group
- Rotate Sections
- Chunk Processing Problems

---

# Master Pattern Recognition

看到 recursion linked list，先问它属于哪一类。

---

## Type 1 — Reverse Family

Question:

```text
是不是在 recursion unwind phase 修改 pointer？
```

Typical sign:

```java
head.next.next = head;
head.next = null;
```

Core idea:

```text
后面的链表已经反转好了
当前节点只负责把边反过来
```

---

## Type 2 — Merge Family

Question:

```text
是不是当前节点接 recursive result？
```

Typical sign:

```java
node.next = recurse(...)
return node;
```

Core idea:

```text
当前节点只负责选择自己
剩余链表交给 recursion
```

---

## Type 3 — Chunk Family

Question:

```text
是不是先处理当前 block，再 recurse 剩余？
```

Typical sign:

```java
process current group
head.next = recurse(rest)
return newHead
```

Core idea:

```text
每一层 recursion 只处理一个局部 block
```

---

# Most Important Recursive Intuition

Linked List recursion 的本质是：

```text
recursive function = 帮我处理剩余链表
```

你每一层只需要想清楚：

```text
当前这一层负责什么？
剩下的交给谁？
返回值是谁？
指针有没有断干净？
```

---

# Interview Reality

## 高频 iterative patterns

面试里 linked list 更常考：

- Reverse Linked List iterative
- Fast / Slow Pointer
- Merge Two Lists iterative
- Cycle Detection
- Reorder List
- Remove Nth Node From End
- Reverse Nodes in K Group

## Recursive linked list

会问，但不是主流。

更多用于测试：

- pointer 理解
- recursion intuition
- call stack 理解
- 是否能写出另一种解法

## NG / Intern Preparation Standard

你不需要刷很多 recursive linked list 题。

但这三个 anchor 要做到：

1. 不看答案能默写
2. 能解释每一行 pointer
3. 能画 recursive stack
4. 能说清楚 base case
5. 能说清楚 return value
6. 能从 iterative 转 recursive
7. 能从 recursive 转 iterative

---

# Quick Summary

## Reverse Family

```java
ListNode newHead = reverse(head.next);
head.next.next = head;
head.next = null;
return newHead;
```

Mental model:

```text
回溯阶段反转边
```

---

## Merge Family

```java
node.next = recurse(...);
return node;
```

Mental model:

```text
当前节点接住递归结果
```

---

## Chunk Family

```java
process current block
head.next = recurse(rest)
return newHead
```

Mental model:

```text
局部处理 + 剩余交给 recursion
```

---

# Final Rule

如果你看到 linked list recursion 想不出来，就问自己：

```text
1. base case 是什么？
2. recursion 帮我处理哪一段？
3. 当前层需要改哪条 pointer？
4. return 的 head 是谁？
5. 是否需要断开旧 pointer？
```

这五个问题能覆盖大部分 linked list recursion 面试题。