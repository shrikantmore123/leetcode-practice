# 4. Median of Two Sorted Arrays (LeetCode 4)

**Difficulty:** Hard

**Topics:** Array

**Tags:** Brute Force, Basics, Beginner-Friendly

**LeetCode Link:** https://leetcode.com/problems/median-of-two-sorted-arrays/

---

### Problem Statement

Given two sorted arrays `nums1` and `nums2` of size `m` and `n` respectively, return the median of the two sorted arrays.

The overall run time complexity should be `O(log (m+n))`.

---

### Example 1:

**Input:** nums1 = [1,3], nums2 = [2]

**Output:** 2.00000

**Explanation:** merged array = [1,2,3] and median is 2.

### Example 2:

**Input:** nums1 = [1,2], nums2 = [3,4]

**Output:** 2.50000

**Explanation:** merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.

---

### Constraints:

- `nums1.length == m`

- `nums2.length == n`

- `0 <= m <= 1000`

- `0 <= n <= 1000`

- `1 <= m + n <= 2000`

- `-10⁶ <= nums1[i], nums2[i] <= 10⁶`

---

### Approach (Brute Force) 

- Copy both arrays into a new array.

- Sort the new merged array.

- If total length is odd → return middle element.

- If even → return average of the two middle elements.

---

### Code

```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int m = nums1.length;
        int n = nums2.length;
        int size = m + n;
        int newArr[] = new int[size];
        
        for (int i = 0; i < m; i++) {
            newArr[i] = nums1[i];
        }

        for (int i = 0; i < n; i++) {
            newArr[m + i] = nums2[i];
        }

        Arrays.sort(newArr);

        if(size % 2 == 1) {
            int index = size / 2;
            return newArr[index];
        } else {
            int mid = size / 2;
            return (newArr[mid - 1] + newArr[mid]) / 2.0;
        }
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `O(n log n)`

- Space Complexity: `O(n)`

---

### Notes

- This brute-force approach is simple and easy to implement.

- Correct but NOT optimal - does not follow the required O(log (m+n)) solution.

- Optimal solution uses binary search partitioning on the smaller array.

- Useful for understanding how median works when merging arrays.