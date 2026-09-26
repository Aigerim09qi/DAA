# Task: Binary Search

## 1. Problem
We have a sorted array of numbers and a target number. We need to find the index of the target number in the array. If it's not there, we return -1. The main requirement is to solve the problem with O(log n) time complexity.

## 2. Approach
I used the classic Binary Search approach:
- Created two pointers: `left` pointing to the first element (index 0) and `right` pointing to the last element.
- Used a `while` loop that runs as long as `left <= right`.
- Inside the loop, calculated the middle index `mid` using `left + (right - left) / 2` to avoid any overflow issues.
- If `nums[mid]` is equal to target, we found it and return `mid`.
- If `nums[mid]` is smaller than target, it means the target is on the right side, so I move `left = mid + 1`.
- Otherwise, if `nums[mid]` is bigger, I search the left side by moving `right = mid - 1`.
- If the loop finishes without finding the target, return -1.

## 3. Time Complexity
**Time Complexity:** O(log n)

**Explanation:**  
In every step of the loop, we cut the array in half. So even if the array is very large, the number of steps grows very slowly (logarithmically). In the worst case, it takes at most log2(n) steps to find the element or realize it is not there.

## 4. Space Complexity
**Space Complexity:** O(1)

**Explanation:**  
I only use a few variables (`left`, `right`, and `mid`). Since I didn't create any new arrays or lists, the extra memory used is constant and doesn't depend on the array size.

## 5. Reflection / Improvement
- **Is there a more efficient approach?**  
  No, O(log n) is already the best possible time complexity for searching in a sorted array.
- **What would you need to change?**  
  Nothing, the code is already simple.
- **What complexity could the improved solution achieve?**  
  It is already at the best complexity: O(log n) time and O(1) space.