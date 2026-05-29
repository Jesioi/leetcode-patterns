# Course Schedule

Pattern:
Topological Sort (Kahn BFS)

## Core Insight

```text
pre -> course
```

finish prerequisite
→ unlock course

---

## Core Invariant

```text
indegree[i]
=
how many prerequisites are still unfinished
```

```text
queue stores:
all currently available courses
(indegree == 0)
```

---

## Mental Model

```text
take one available course
→ unlock next courses
→ indegree--
→ new indegree 0 enters queue

---

pre -> course

indegree[i]
=
这门课还剩多少 prerequisite 没完成

queue 里永远存：
当前可以学的课（indegree == 0）

学掉一门课：
它解锁的课程 indegree--

新的 indegree == 0：
说明 prerequisite 全完成
入 queue

最后：
count == numCourses
说明没有 cycle
```

---

## Failure Condition

```text
cycle
=
some courses can never reach indegree 0
```

---

## Success Condition

```text
processed course count == numCourses
```

---

## Template

```java
build graph
build indegree

queue all indegree 0

while (!queue.isEmpty()) {

    take course

    for (next : neighbors) {
        indegree[next]--;

        if (indegree[next] == 0) {
            queue.offer(next);
        }
    }
}
```

---

## Common Bugs

- edge direction reversed
- indegree updated wrong side
- only processing one indegree 0 node
- forgetting all initial indegree 0 nodes

---

## Representative Problems

- Course Schedule
- Course Schedule II
- Alien Dictionary
