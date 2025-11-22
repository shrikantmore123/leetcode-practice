# 217. Contains Duplicate (LeetCode 217)

**Difficulty:** Easy

**Topics:** Array

**Tags:** Brute Force, Duplicate Check, Basic Array Traversal

**LeetCode Link:** https://leetcode.com/problems/contains-duplicate/

---

### Problem Statement

Given an integer array `nums`, return `true` if any value appears at least twice in the array, and return `false` if every element is distinct.

---

### Example 1:

**Input:** nums = [1,2,3,1]

**Output:** true

**Explanation:** The element 1 occurs at the indices 0 and 3.

### Example 2:

**Input:** nums = [1,2,3,4]

**Output:** false

**Explanation:** All elements are distinct.

### Example 3:

**Input:** nums = [1,1,1,3,3,4,3,2,4,2]

**Output:** true

---

### Constraints:

- `1 <= nums.length <= 10⁵`

- `-10⁹ <= nums[i] <= 10⁹`

---

### Approach (Brute Force) 

- Compare every element with every other element using two nested loops.

- If any pair matches → duplicate found → return true.

- If no pair matches → return false.

- Simple but very slow for large inputs.

---

### Code

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        for(int i = 0; i < nums.length - 1; i++) {
            for(int j = i + 1; j < nums.length; j++) {
                if(nums[i] == nums[j]) {
                    return true;
                }
            }
        }
        return false;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `O(n²)`

- Space Complexity: `O(1)`

---

### Notes

- Brute force is easy to understand but inefficient for large arrays.

- Useful for understanding nested loop pair comparisons.