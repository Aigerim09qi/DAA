# Linked List Cycle

## 1. Problem

We are given the head of a linked list.

We need to check if the linked list has a cycle.

A cycle means that after following the `next` pointers, we can reach a node that we have already visited.

For example:

```text
3 → 2 → 0 → -4
    ↑         |
    └─────────┘
```

Here the last node points back to node `2`, so the answer is `true`.

If the list ends with `null`, there is no cycle and the answer is `false`.

## 2. Approach

I use a `HashSet` to store the nodes that I have already visited.

I start from `head` and use a pointer called `current`.

For every node, I check if it is already in the `HashSet`.

* If it is already there, there is a cycle, so I return `true`.
* If it is not there, I add it to the set.
* Then I move to the next node.

If `current` becomes `null`, it means that the list has no cycle, so I return `false`.

### Example Trace

For this list:

```text
3 → 2 → 0 → -4
    ↑         |
    └─────────┘
```

The steps are:

```text
current = 3
visited = {}

Add 3

current = 2
visited = {3}

Add 2

current = 0
visited = {3, 2}

Add 0

current = -4
visited = {3, 2, 0}

Add -4

current = 2
visited = {3, 2, 0, -4}

2 is already in visited, so return true.
```

For a list without a cycle:

```text
1 → 2 → 3 → null
```

we visit all three nodes and then reach `null`.

So the result is `false`.

I store the `ListNode` objects in the `HashSet`, not only their values. This is important because different nodes can have the same value.

## 3. Time Complexity

**Time Complexity: O(n)**

I go through the list once. Each node is checked and added to the `HashSet` at most once.

## 4. Space Complexity

**Space Complexity: O(n)**

In the worst case, the `HashSet` can contain all nodes of the linked list.

## 5. Reflection / Improvement

My solution is simple and easy to understand, but it uses extra memory for the `HashSet`.

A better solution is Floyd's Cycle Detection Algorithm.

It uses two pointers:

* `slow` moves one step at a time.
* `fast` moves two steps at a time.

If there is a cycle, the two pointers will eventually meet.

This solution also has `O(n)` time complexity, but its space complexity is `O(1)`.

So the main improvement would be reducing the extra space from `O(n)` to `O(1)`.
