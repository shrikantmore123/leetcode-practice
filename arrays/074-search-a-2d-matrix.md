# 74. Search a 2D Matrix (LeetCode 74)

**Difficulty:** Medium

**Topics:** Array, Binary Search, Matrix

**Tags:** Matrix Search, Staircase Search, Two Pointers

**LeetCode Link:** https://leetcode.com/problems/search-a-2d-matrix/

---

### Problem Statement

You are given an `m x n` integer matrix `matrix` with the following two properties:

- Each row is sorted in non-decreasing order.

- The first integer of each row is greater than the last integer of the previous row.

Given an integer `target`, return `true` if `target` is in `matrix` or `false` otherwise.

You must write a solution in `O(log(m * n))` time complexity.

---

### Example 1:

![Search a 2D Matrix](https://assets.leetcode.com/uploads/2020/10/05/mat.jpg)

**Input:** matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3

**Output:** true

### Example 2:

**Input:** matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13

**Output:** false

---

### Constraints:

- `m == matrix.length`

- `n == matrix[i].length`

- `1 <= m, n <= 100`

- `-10⁴ <= matrix[i][j], target <= 10⁴`

---

### Approach (Top-Right Traversal / Staircase Search)

- Start from the top-right corner.

- If current element equals target → return true.

- If target is smaller → move left.

- If target is larger → move down.

- Continue until bounds are valid.

---

### Code

```java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int row = 0, col = matrix[0].length - 1;

        while (row < matrix.length && col >= 0) {
            if(matrix[row][col] == target) {
                return true;
            }
            else if(target < matrix[row][col]) {
                col--;
            }
            else {
                row++;
            }
        }

        return false;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(m + n)`

- Space Complexity: `o(1)`

---

### Notes

- This is a staircase search approach.

- Does not meet the required o(log(m * n)) but still efficient.

- Optimal solution uses binary search treating matrix as 1D.