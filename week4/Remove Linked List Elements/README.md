# Remove Linked List Elements

## 1. Problem

I need to remove every node whose value equals the given number `val`.

## 2. Approach

I create a dummy node before the head. Then I use a pointer called `current` to check the next node.

If the next node contains `val`, I skip it. Otherwise, I move `current` forward.

**Example:**

Input: `1 -> 2 -> 6 -> 3 -> 6 -> 4`, `val = 6`

- I start with the dummy node before `1`.
- I check `1`. It is not `6`, so I move forward.
- I check `2`. It is not `6`, so I move forward.
- The next node is `6`, so I skip it and connect `2` directly to `3`.
- I continue through the list and remove the second `6` in the same way.
- I reach the end of the list.

Output: `1 -> 2 -> 3 -> 4`

The dummy node is useful because the first node might also need to be removed.

## 3. Time Complexity

**Time Complexity: O(n)**

I examine each node at most once, where `n` is the number of nodes in the list.

**Space Complexity: O(1)**

I only create one dummy node and use one pointer. I do not create a new list.

## 4. Reflection / Improvement

The solution is already efficient. Without a dummy node, I could first remove matching nodes from the beginning and then process the remaining list. The dummy node makes the code simpler because I can handle all nodes in the same way.