287. Find the Duplicate Number (LeetCode 287)

**Difficulty:** Medium

**Topics:** Array, Two Pointers, Binary Search

**Tags:** Floyd’s Cycle Detection, Linked List Concept, Fast & Slow Pointers

**LeetCode Link:** https://leetcode.com/problems/find-the-duplicate-number/

---

### Problem Statement

Given an array of integers `nums` containing `n + 1` integers where each integer is in the range `[1, n]` inclusive.

There is only one repeated number in `nums`, return this repeated number.

You must solve the problem without modifying the array `nums` and using only constant extra space.



---

### Example 1:

**Input:** nums = [1,3,4,2,2]

**Output:** 2

### Example 2:

**Input:** nums = [3,1,3,4,2]

**Output:** 3

### Example 3:

**Input:** nums = [3,3,3,3,3]

**Output:** 3

---

### Constraints:

- `1 <= n <= 10⁵`

- `nums.length == n + 1`

- `1 <= nums[i] <= n`

- All the integers in `nums` appear only once except for precisely one integer which appears two or more times.

---

### Approach (Two Pointers)

- Approach (Floyd’s Cycle Detection / Tortoise & Hare)

- Treat array as a linked list:

    - Index → node

    - Value → next pointer

- Since duplicate exists → cycle must exist

- Step 1: Detect cycle

    - Move `slow` by 1 step

    - Move `fast` by 2 steps

    - They will meet inside the cycle

- Step 2: Find entry point of cycle

    - Start another pointer from beginning

    - Move both pointers one step
    
    - Meeting point = duplicate number

---

### Code

```java
class Solution {
    public int findDuplicate(int[] nums) {
        int slow = nums[0];
        int fast = nums[0];

        while(true) {
            slow = nums[slow];
            fast = nums[nums[fast]];

            if(slow == fast) {
                break;
            }
        }

        int slow2 = nums[0];

        while(slow != slow2) {
            slow = nums[slow];
            slow2 = nums[slow2];
        }

        return slow;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- Does not modify array (important constraint).

- Uses constant space.

- One of the most important cycle detection problems.

- Same concept as linked list cycle detection.