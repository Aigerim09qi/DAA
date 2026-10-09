# Merge Two Sorted Lists

## 1. Problem

We have two sorted linked lists, `list1` and `list2`.

We need to merge them into one sorted linked list.

For example:

```text
list1: 1 → 2 → 4
list2: 1 → 3 → 4
```

The result should be:

```text
1 → 1 → 2 → 3 → 4 → 4
```

The important thing is that the new list should use the nodes from the original lists.

---

## 2. Approach

I use two pointers, `list1` and `list2`, to go through both lists.

I also create a temporary `dummy` node. It helps me build the result list more easily.

Then I use another pointer called `current`.

At each step, I compare the values of the current nodes:

```text
list1.val and list2.val
```

If the value in `list1` is smaller or equal, I add that node to the result.

Otherwise, I add the node from `list2`.

After adding a node, I move its list pointer to the next node.

I continue until one of the lists becomes empty.

After that, I add the remaining part of the other list to the result.

### Example

Start with:

```text
list1: 1 → 2 → 4
list2: 1 → 3 → 4
```

First, compare `1` and `1`.

They are equal, so I take the first `1`.

```text
result: 1
```

Now:

```text
list1: 2 → 4
list2: 1 → 3 → 4
```

Compare `2` and `1`.

`1` is smaller, so I take it.

```text
result: 1 → 1
```

Next:

```text
list1: 2 → 4
list2: 3 → 4
```

`2` is smaller than `3`, so I take `2`.

```text
result: 1 → 1 → 2
```

Then I take `3`:

```text
result: 1 → 1 → 2 → 3
```

Then the two `4` values are added.

Final result:

```text
1 → 1 → 2 → 3 → 4 → 4
```

---

## 3. Time Complexity

**Time Complexity: O(n + m)**

`n` is the number of nodes in `list1` and `m` is the number of nodes in `list2`.

I go through the nodes of both lists only once, so the total number of operations is proportional to `n + m`.

---

## 4. Space Complexity

**Space Complexity: O(1)**

I only use a few extra variables:

```text
dummy
current
```

I do not create a new list with new nodes. I reuse the nodes from the original lists.

Therefore, the extra space is constant.

---

## 5. Reflection / Improvement

I think this is already a good solution because its time complexity is `O(n + m)`.

There is no need to sort the lists again because they are already sorted.


So I would keep my iterative solution because it is simple and uses `O(1)` extra space.
