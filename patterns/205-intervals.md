# Intervals

Core Pattern:
Process overlapping ranges
on a number line.

Core Insight:
Sort intervals first.

Once sorted,
overlap decisions become local.

Core Components:

- sort by start
- compare current interval
- merge or split
- track previous interval

Recognition Signals:

- interval
- meeting
- schedule
- time range
- overlap
- calendar
- merge ranges

Template Signal:

- merge intervals
- insert interval
- meeting rooms
- non-overlapping intervals
- interval scheduling

Key Questions:

Do these intervals overlap?

If yes:
merge them

If no:
start a new interval

Overlap Condition:

current.start <= previous.end

No Overlap:

current.start > previous.end

Common Workflow:

1. Sort intervals
2. Process from left to right
3. Compare with previous interval
4. Merge or append

Common Bugs:

- forgetting to sort first
- incorrect overlap condition
- updating wrong end value
- not handling final interval
- modifying input unexpectedly

Representative Problems:

- Merge Intervals
- Insert Interval
- Meeting Rooms
- Meeting Rooms II
- Non-overlapping Intervals

Mental Model:

Sort intervals on a timeline.

Walk from left to right.

Whenever two intervals touch,
decide whether they should become
one larger interval.

Typical Complexity:

Sort:
O(n log n)

Scan:
O(n)

Total:
O(n log n)

## Common Subpatterns:

1. Merge Overlaps

Examples:

- Merge Intervals
- Insert Interval

Goal:

Combine overlapping intervals

---

2. Count Resources

Examples:

- Meeting Rooms II

Goal:

How many rooms/resources
are needed simultaneously?

Common Tools:

- min heap
- sweep line

---

3. Greedy Interval Scheduling

Examples:

- Non-overlapping Intervals

Goal:

Keep maximum intervals
or remove minimum intervals

Common Strategy:

Sort by end time
