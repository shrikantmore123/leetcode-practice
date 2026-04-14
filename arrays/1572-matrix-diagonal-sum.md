# 1572. Matrix Diagonal Sum (LeetCode 1572)

**Difficulty:** Easy

**Topics:** Array, Matrix

**Tags:** Matrix Traversal, Diagonals, Simulation

**LeetCode Link:** https://leetcode.com/problems/matrix-diagonal-sum/

---

### Problem Statement

Given a square matrix `mat`, return the sum of the matrix diagonals.

Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.

---

### Example 1:

![Matrix Diagonal Sum](https://assets.leetcode.com/uploads/2020/08/14/sample_1911.png)

**Input:** height = mat = [[1,2,3],
              [4,5,6],
              [7,8,9]]

**Output:** 25

**Explanation:** Diagonals sum: 1 + 5 + 9 + 3 + 7 = 25.
Notice that element mat[1][1] = 5 is counted only once.

### Example 2:

**Input:** mat = [[1,1,1,1],
              [1,1,1,1],
              [1,1,1,1],
              [1,1,1,1]]

**Output:** 8

### Example 3:

**Input:** mat = [[5]]

**Output:** 5

---

### Constraints:

- `n == mat.length == mat[i].length`

- `1 <= n <= 100`

- `1 <= mat[i][j] <= 100`

---

### Approach (Single Loop Diagonal Traversal)

- CTraverse the matrix using a single loop.

- Add primary diagonal → `mat[i][i]`

- Add secondary diagonal → `mat[i][n - i - 1]`

- Avoid double counting when `i == n - i - 1`.

---

### Code

```java
class Solution {
    public int diagonalSum(int[][] mat) {
        int sum = 0;

        for(int i = 0; i < mat.length; i++) {
            // Primary Diagonal 
            sum += mat[i][i];

            // Secondary Diagonal
            if(i != mat.length - 1 - i){
                sum += mat[i][mat.length - i - 1];
            }
        }

        // Brute Force : O(n^2)
        // for(int i = 0; i < mat.length; i++) {
        //     for(int j = 0; j < mat[0].length; j++) {
        //         if(i == j) {
        //             sum += mat[i][j];
        //         }
        //         else if(i + j == mat.length - 1) {
        //             sum += mat[i][j];
        //         }
        //     }
        // }

        return sum;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- Efficient solution using a single loop instead of nested loops.

- Avoids double counting the middle element.

- Brute force approach would take `o(n²)`.