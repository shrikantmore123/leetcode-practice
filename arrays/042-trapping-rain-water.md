# 42. Trapping Rain Water (LeetCode 42)

**Difficulty:** Hard

**Topics:** Array

**Tags:** Prefix Max, Suffix Max, Water Trapping Pattern


**LeetCode Link:** https://leetcode.com/problems/trapping-rain-water/

---

### Problem Statement

Given `n` non-negative integers representing an elevation map where the width of each bar is `1`, compute how much water it can trap after raining.

---

### Example 1:

![Trapped Rainwater](https://assets.leetcode.com/uploads/2018/10/22/rainwatertrap.png)

**Input:** height = [0,1,0,2,1,0,1,3,2,1,2,1]

**Output:** 6

**Explanation:** The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.

### Example 2:

**Input:** height = [4,2,0,3,2,5]

**Output:** 9

---

### Constraints:

- `n == height.length`

- `1 <= n <= 2 * 10⁴`

- `0 <= height[i] <= 10⁵`

---

### Approach (Prefix Max & Suffix Max Arrays)

- Compute `leftMax[]` → maximum height from left up to index `i`.

- Compute `rightMax[]` → maximum height from right up to index `i`.

- For each index:

- Water level = `min(leftMax[i], rightMax[i])`

- Trapped water = `waterLevel - height[i]`

- Sum all trapped water values.

---

### Code

```java
class Solution {
    public int trap(int[] height) {
        int n = height.length;

        // calculate left max boundary - array
        int leftMax[] = new int[n];
        leftMax[0] = height[0];

        for(int i = 1; i < n; i++) {
            leftMax[i] = Math.max(height[i], leftMax[i - 1]);
        }

        // calculate right max boundary - array
        int rightMax[] = new int[n];
        rightMax[n - 1] = height[n - 1];
        for(int i = n - 2; i >= 0; i--) {
            rightMax[i] = Math.max(height[i], rightMax[i + 1]);
        }

        // calculate trapped water
        int trappedWater = 0;

        for(int i = 0; i < n; i++) {
            // waterLevel = min(leftMax boundary, rightMax boundary)
            int waterLevel = Math.min(leftMax[i], rightMax[i]);

            // trappedWater = waterLevel - height
            trappedWater += waterLevel - height[i];
        }

        return trappedWater;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(n)`

---

### Notes

- This approach uses extra space for left and right max arrays.

- Efficient compared to brute force (which is o(n²)).

- Classic problem to understand water trapping and boundary concepts.