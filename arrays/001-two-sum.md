# 1. Two Sum (LeetCode 1)

**Difficulty:** Easy

**Topics:** Array

**Tags:** Brute Force, Pair Sum Pattern, Basics, Beginner-Friendly


**LeetCode Link:** https://leetcode.com/problems/two-sum/

---

### Problem Statement

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

---

### Example 1:

**Input:** nums = [2,7,11,15], target = 9

**Output:** [0,1]

**Explanation:** Because nums[0] + nums[1] == 9, we return [0, 1].

### Example 2:

**Input:** nums = [3,2,4], target = 6

**Output:** [1,2]

### Example 3:

**Input:** nums = [3,3], target = 6

**Output:** [0,1]

---

### Constraints:

- `2 <= nums.length <= 10⁴`

- `-10⁹ <= nums[i] <= 10⁹`

- `-10⁹ <= target <= 10⁹`

- Only one valid answer exists.

**Follow-up:** Can you come up with an algorithm that is less than O(n²) time complexity?


---

### Approach (Brute Force) 

- Check all pairs using two nested loops.

- Return the pair that sums to the target.

- This is the simplest approach but not optimal.

---

### Code

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int arrSize = nums.length, res = 0;

        for(int i = 0; i < arrSize - 1; i++) {
            for(int j = i + 1; j < arrSize; j++) {
                res = nums[i] + nums[j];
                if(res == target) {
                    return new int[] {i, j};
                }
            }
        }
        return new int[] {};
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `O(n²)`

- Space Complexity: `O(1)`

---

### Notes

- Good introductory problem for understanding array traversal.

- Useful pattern for many "two numbers sum to target" problems.

- Always check constraints to choose the correct approach.