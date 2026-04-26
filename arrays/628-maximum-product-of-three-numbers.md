# 628. Maximum Product of Three Numbers (LeetCode 628)

**Difficulty:** Easy

**Topics:** Array, Sorting

**Tags:** Sorting, Greedy, Max Product

**LeetCode Link:** https://leetcode.com/problems/maximum-product-of-three-numbers/

---

### Problem Statement

Given an integer array `nums`, find three numbers whose product is maximum and return the maximum product.

---

### Example 1:

**Input:** nums = [1,2,3]

**Output:** 6

### Example 2:

**Input:** nums = [1,2,3,4]

**Output:** 24

### Example 3:

**Input:** nums = [-1,-2,-3]

**Output:** -6

---

### Constraints:

- `13 <= nums.length <= 10⁴`

- `-1000 <= nums[i] <= 1000`

---

### Approach (Sorting + Comparison)

- Sort the array.

- Two possible maximum products:
    
    - Product of three largest numbers

    - Product of two smallest (negative) numbers and the largest number

- Return the maximum of both.
---

### Code

```java
class Solution {
    public int maximumProduct(int[] nums) {
        Arrays.sort(nums);
        int n = nums.length;

        int product1 = nums[n - 1] * nums[n - 2] * nums[n - 3];
        int product2 = nums[n - 1] * nums[0] * nums[1];

        if (product1 > product2) {
            return product1;
        }

        return product2;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n log n)`

- Space Complexity: `o(1)`

---

### Notes

- Negative numbers can produce a larger product when multiplied together.

- Always check both combinations.

- Sorting simplifies finding extremes.

- Can be optimized to `o(n)` by tracking max/min values.