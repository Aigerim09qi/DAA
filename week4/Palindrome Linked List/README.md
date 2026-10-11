# Palindrome Linked List

## 1. Problem

I need to check whether a linked list is a palindrome. It means the values are the same when read from left to right and from right to left.

## 2. Approach

I copy all node values into an `ArrayList`. Then I compare the first and last elements, moving toward the middle.

**Example 1:**

Input: `1 -> 2 -> 2 -> 1`

- First, I copy the values into an array: `[1, 2, 2, 1]`.
- I compare the first `1` with the last `1`. They match.
- Then I compare the second `2` with the third `2`. They also match.
- All pairs match, so I return `true`.

**Example 2:**

Input: `1 -> 2 -> 3`

- I copy the values into an array: `[1, 2, 3]`.
- I compare the first value, `1`, with the last value, `3`.
- They are different, so I return `false`.

This approach is easy to understand because an array lets me access elements from both ends.

## 3. Time Complexity

**Time Complexity: O(n)**

I traverse the linked list once to copy its values. Then I compare pairs of elements, which takes at most O(n) time. Together, these operations are O(n).

**Space Complexity: O(n)**

I store all `n` values in an additional array list.

## 4. Reflection / Improvement

A more space-efficient approach is to find the middle of the linked list, reverse the second half, and compare both halves.

This can achieve O(n) time and O(1) extra space. However, reversing the list requires more pointer operations, so I chose the array approach because it is easier to understand.