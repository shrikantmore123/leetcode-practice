# 1486. XOR Operation in an Array (LeetCode 1486)

**Difficulty:** Easy

**Topics:** Array, Bit Manipulation

**Tags:** XOR, Pattern, Bit Manipulation

**LeetCode Link:** https://leetcode.com/problems/xor-operation-in-an-array/

---

### Problem Statement

You are given an integer `n` and an integer `start`.

Define an array `nums` where `nums[i] = start + 2 * i` (0-indexed) and `n == nums.length`.

Return the bitwise XOR of all elements of `nums`.
---

### Example 1:

**Input:** n = 5, start = 0

**Output:** 8

**Explanation:** Array nums is equal to [0, 2, 4, 6, 8] where (0 ^ 2 ^ 4 ^ 6 ^ 8) = 8.
Where "^" corresponds to bitwise XOR operator.

### Example 2:

**Input:** n = 4, start = 3

**Output:** 8

**Explanation:** Array nums is equal to [3, 5, 7, 9] where (3 ^ 5 ^ 7 ^ 9) = 8.

---

### Constraints:

- `1 <= n <= 1000`

- `0 <= start <= 1000`

- `n == nums.length`

---

### Approach (Iterative XOR Calculation)

- Initialize result with first element.

- Iterate from `1` to `n - 1`.

- Compute each element using formula:

    - `start + 2 * i`

- Apply XOR with result.

---

### Code

```java
class Solution {
    public int xorOperation(int n, int start) {
        int result = start;
        for(int i = 1; i < n; i++) {
            result ^= start + 2 * i;
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

- OXOR properties:
    
    - a ^ a = 0

    - a ^ 0 = a

- No need to explicitly create array.

- Efficient in both time and space.