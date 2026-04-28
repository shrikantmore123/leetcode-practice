# 977. Squares of a Sorted Array (LeetCode 977)

**Difficulty:** Easy

**Topics:** Array, Two Pointers

**Tags:** Two Pointers, Sorting, Transformation

**LeetCode Link:** https://leetcode.com/problems/squares-of-a-sorted-array/

---

### Problem Statement

Given an integer array `nums` sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

---

### Example 1:

**Input:** nums = [-4,-1,0,3,10]

**Output:** [0,1,9,16,100]

**Explanation:** After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].

### Example 2:

**Input:** nums = [-7,-3,2,3,11]

**Output:** [4,9,9,49,121]

---

### Constraints:

- `1 <= nums.length <= 10⁴`

- `-10⁴ <= nums[i] <= 10⁴`

- `nums` is sorted in non-decreasing order.

---

### Approach (Two Pointers)

- Square all elements first.

- Use two pointers:

    - `left` → start

    - `right` → end

- Place larger square at the end of result array.

- Move pointers accordingly.

---

### Code

```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        // int sqrArr[] = new int[nums.length];
        
        // for(int i = 0; i < nums.length; i++) {
        //     sqrArr[i] = nums[i] * nums[i];
        // }

        // Arrays.sort(sqrArr);

        // return sqrArr;

        int n = nums.length;
        int result[] = new int[n];
        
        for(int i = 0; i < n; i++) {
            nums[i] = nums[i] * nums[i];
        }

        int left = 0;
        int right = n - 1;
        int insertPos = n - 1;

        while(left <= right) {
            if(nums[left] > nums[right]) {
                result[insertPos] = nums[left];
                left++;
            } else {
                result[insertPos] = nums[right];
                right--;
            }

            insertPos--;
        }

        return result;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- Efficient alternative to sorting approach `(o(n log n))`.

- Uses two-pointer technique to maintain order.

- Squaring first simplifies comparison logic.

- Classic pattern for sorted array transformations.