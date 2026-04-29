# 136. Single Number (LeetCode 136)

**Difficulty:** Easy

**Topics:** Array, Bit Manipulation

**Tags:** XOR, Bit Manipulation, Optimal

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

### Approach (XOR / Bit Manipulation)

- XOR all elements in the array.

- Properties of XOR:

    - a ^ a = 0

    - a ^ 0 = a

- All duplicate numbers cancel out.

- Remaining value is the single number.

---

### Code

```java
class Solution {
    public int singleNumber(int[] nums) {
        int result = 0;
        int n = nums.length;
        
        for(int i = 0; i < n; i++) {
            result = result ^ nums[i];
        }

        return result;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `O(1)`

---

### Notes

- Optimal solution compared to sorting approach.

- Uses bit manipulation concept.

- No extra space required.