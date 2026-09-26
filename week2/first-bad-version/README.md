# Task: First Bad Version

## 1. Problem
We have versions from 1 to n. Once a version gets corrupted (bad), all the versions after it are also bad. We need to find the very first bad version using the `isBadVersion(version)` function, and we should make as few calls to this function as possible.

## 2. Approach
I solved this using Binary Search:
- Set `left = 1` and `right = n`.
- Used a `while` loop with `left < right`.
- Found the middle point `mid` using `left + (right - left) / 2`.
- Checked `isBadVersion(mid)`:
    - If it returns `true`, this version is bad, so the *first* bad version could be this one or somewhere to the left. So I set `right = mid`.
    - If it returns `false`, this version is fine, which means the bad version must be strictly to the right. So I set `left = mid + 1`.
- When `left` and `right` meet, the loop ends, and `left` holds the answer.

## 3. Time Complexity
**Time Complexity:** O(log n)

**Explanation:**  
Instead of checking every version one by one, we cut the search range in half on each step. This keeps the number of API calls very low, giving us an O(log n) time complexity.

## 4. Space Complexity
**Space Complexity:** O(1)

**Explanation:**  
The algorithm only uses three variables (`left`, `right`, `mid`). No extra space or arrays are created, so memory usage is O(1).

## 5. Reflection / Improvement
- **Is there a more efficient approach?**  
  No, O(log n) is the fastest way to find the boundary here.
- **What would you need to change?**  
  The main trick was using `right = mid` instead of `mid - 1` when finding a bad version, so we don't accidentally skip the answer.
- **What complexity could the improved solution achieve?**  
  No further improvement is needed for the required time complexity.