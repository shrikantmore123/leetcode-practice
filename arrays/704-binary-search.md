# 704. Binary Search (LeetCode 704)

**Difficulty:** Easy

**Topics:** Array, Binary Search

**Tags:** Binary Search, Divide and Conquer, Searching

**LeetCode Link:** https://leetcode.com/problems/binary-search/

---

### Problem Statement

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search `target` in `nums`. If `target` exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

---

### Example 1:

**Input:** nums = [-1,0,3,5,9,12], target = 9

**Output:** 4

**Explanation:** 9 exists in nums and its index is 4

### Example 2:

**Input:** nums = [-1,0,3,5,9,12], target = 2

**Output:** -1

**Explanation:** 2 does not exist in nums so return -1

---

### Constraints:

- `1 <= nums.length <= 10⁴`

- `-10⁴ < nums[i], target < 10⁴`

- All the integers in `nums` are unique.

- `nums` is sorted in ascending order.

---

### Approach (Binary Search)

- Initialize `start = 0`, `end = n - 1`.

- Find middle index using:

    - `mid = start + (end - start) / 2` (prevents overflow)

- Compare:

    - If equal → return index

    - If target is greater → search right half

    - If smaller → search left half

- Repeat until found or range becomes invalid.

---

### Code

```java
class Solution {
    public int search(int[] nums, int target) {
        int start = 0;
        int end = nums.length - 1;

        while(start <= end) {
            // int mid = (start + end) / 2
            int mid = start + (end  - start) / 2;

            if(nums[mid] == target) {
                return mid;
            } else if(nums[mid] < target) {
                start = mid + 1;
            } else {
                end = mid - 1;
            }
        }

        return -1;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(log n)`

- Space Complexity: `o(1)`

---

### Notes

- Efficient search on sorted arrays.

- Always use `start + (end - start) / 2` to avoid overflow.

- Reduces search space by half each iteration.