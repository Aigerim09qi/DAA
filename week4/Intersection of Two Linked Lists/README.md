# Intersection of Two Linked Lists

## 1. Problem

I need to find the node where two linked lists intersect. If they do not share a node, I return `null`.

Two nodes with the same value are not necessarily the same node. The lists must share the actual node.

## 2. Approach

I use two pointers, `a` and `b`. The first starts at list A, and the second starts at list B.

Both pointers move forward one node at a time. When a pointer reaches the end, I move it to the beginning of the other list.

**Example:**

List A: `1 -> 2 -> 3 -> 8 -> 9`

List B: `4 -> 5 -> 8 -> 9`

Suppose both lists share the actual nodes `8 -> 9`.

- Pointer `a` starts at `1`, and pointer `b` starts at `4`.
- Both pointers move through their lists.
- When a pointer reaches the end, it starts again from the other list.
- This makes both pointers travel the same total distance.
- They eventually meet at the shared node with value `8`.

Output: the intersection node with value `8`.

If the lists do not intersect, both pointers eventually become `null`, and the method returns `null`.

## 3. Time Complexity

**Time Complexity: O(m + n)**

Here, `m` is the length of list A and `n` is the length of list B. Each pointer traverses both lists at most once.

**Space Complexity: O(1)**

I use only two pointers, regardless of the list sizes.

## 4. Reflection / Improvement

The two-pointer approach is already efficient. A simpler brute-force method would compare every node in A with every node in B, which takes O(m * n) time. The two-pointer solution improves this to O(m + n).