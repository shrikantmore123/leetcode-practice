# 217. Contains Duplicate (LeetCode 217)

**Difficulty:** Easy

**Topics:** Array, Sorting

**Tags:** Sorting, Adjacent Comparison, Duplicate Detection

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

### Approach (Sorting + Adjacent Check)

- Sort the array.

- Check adjacent elements:

- If `nums[i] == nums[i - 1]` → duplicate found.

- If no duplicates found → return false.

- Sorting helps bring duplicates next to each other.

---

### Code

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Arrays.sort(nums);

        for(int i = 1; i < nums.length; i++) {
            if(nums[i] == nums[i - 1]) {
                return true;
            }
        }

        return false;

        // for(int i = 0; i < nums.length - 1; i++) {
        //     if(nums[i] == nums[i + 1]) {
        //         return true;
        //     }
        // }

        // return false;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n log n)`

- Space Complexity: `O(1)`

---

### Notes

- Sorting-based approach is simple and effective.

- Faster than brute force but slower than HashSet approach.