# Remove Duplicates from Sorted List

## 1. Problem

The list is sorted, but some numbers can appear more than once. I need to remove the duplicates and keep only one copy of each number.

## 2. Approach

I use a pointer called `current` to go through the list.

If the current value is equal to the next value, I skip the next node. Otherwise, I move to the next node.

**Example:**

Input: `1 -> 1 -> 2 -> 3 -> 3`

- First, I compare the two nodes with value `1`. They are equal, so I remove the second one.
- Then I compare `1` and `2`. They are different, so I move forward.
- I reach `2` and compare it with `3`. They are different.
- At the end, I find two nodes with value `3` and remove one of them.

Output: `1 -> 2 -> 3`

One important detail is that I should not move `current` after removing a duplicate. There could be more copies of the same number.

## 3. Time Complexity

**Time Complexity: O(n)**

I visit each node at most a constant number of times. Therefore, the time grows linearly with the length of the list.

**Space Complexity: O(1)**

I only use one pointer and do not create another list.

## 4. Reflection / Improvement

The solution is already efficient because the list is sorted. I do not need to sort it or use an extra data structure.