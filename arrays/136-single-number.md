# 217. Contains Duplicate (LeetCode 217)

**Difficulty:** Easy

**Topics:** Array, Sorting

**Tags:** Sorting, Pair Matching, Basics

**LeetCode Link:** https://leetcode.com/problems/single-number/

---

### Problem Statement

Given a non-empty array of integers `nums`, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

---

### Example 1:

**Input:** nums = [2,2,1]

**Output:** 1

### Example 2:

**Input:** nums = [4,1,2,1,2]

**Output:** 4

### Example 3:

**Input:** nums = [1]

**Output:** 1

---

### Constraints:

- `1 <= nums.length <= 3 * 10⁴`

- `-3 * 10⁴ <= nums[i] <= 3 * 10⁴`

- Each element in the array appears twice except for one element which appears only once.

---

### Approach (Sorting + Pair Check)

- Sort the array.

- Traverse in steps of 2:
    
    - Compare adjacent elements.

    - If mismatch found → that element is the single number.

- If all pairs match → last element is the answer.

---

### Code

```java
class Solution {
    public int singleNumber(int[] nums) {
        Arrays.sort(nums);

        for(int i = 0; i < nums.length - 1; i+=2) {
            if(nums[i] != nums[i + 1]) {
                return nums[i];
            }
        }

        return nums[nums.length - 1];
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n log n)`

- Space Complexity: `O(1)`

---

### Notes

- Sorting helps group duplicate elements together.

- Easy to implement but does not meet required o(n) time.

- Optimal solution uses XOR to achieve o(n) time and o(1) space.