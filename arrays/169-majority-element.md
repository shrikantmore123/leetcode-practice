# 169. Majority Element (LeetCode 169)

**Difficulty:** Easy

**Topics:** Array, Sorting

**Tags:** Sorting, Majority Element, Median Concept

**LeetCode Link:** https://leetcode.com/problems/majority-element/

---

### Problem Statement

Given an array `nums` of size `n`, return the majority element.

The majority element is the element that appears more than `⌊n / 2⌋` times. You may assume that the majority element always exists in the array.

---

### Example 1:

**Input:** nums = [3,2,3]

**Output:** 3

### Example 2:

**Input:** nums = [2,2,1,1,1,2,2]

**Output:** 2

---

### Constraints:

- `n == nums.length`

- `1 <= n <= 5 * 10⁴`

- `-10⁹ <= nums[i] <= 10⁹`

- The input is generated such that a majority element will exist in the array.

---

### Approach (Sorting)

- Sort the array.

- The majority element will always be at index n / 2.

- Return the middle element.

---

### Code

```java
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length / 2];
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n log n)`

- Space Complexity: `O(1)`

---

### Notes

- Sorting guarantees the majority element will occupy the middle index.

- Simple and reliable approach.

- Optimal solution uses Boyer-Moore Voting Algorithm → `o(n)` time and `o(1)` space.