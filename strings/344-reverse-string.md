# 344. Reverse String (LeetCode 344)

**Difficulty:** Easy

**Topics:** Array, String, Two Pointers

**Tags:** Two Pointers, In-place Reversal, String Manipulation

**LeetCode Link:** https://leetcode.com/problems/reverse-string/

---

### Problem Statement

Write a function that reverses a string. The input string is given as an array of characters `s`.

You must do this by modifying the input array in-place with `O(1)` extra memory.

---

### Example 1:

**Input:** s = ["h","e","l","l","o"]

**Output:** ["o","l","l","e","h"]

### Example 2:

**Input:** s = ["H","a","n","n","a","h"]

**Output:** ["h","a","n","n","a","H"]

---

### Constraints:

- `1 <= s.length <= 10⁵`

- `s[i]` is a printable ascii character.

---

### Approach (Two Pointers / In-place Swap)

- Use two pointers:

    - start → beginning of array

    - end → end of array

- Swap elements at start and end.

- Move pointers inward until they meet.

---

### Code

```java
class Solution {
    public void reverseString(char[] s) {
        int start = 0;
        int end = s.length - 1;

        while(start <= end) {
            char temp = s[start];
            s[start] = s[end];
            s[end] = temp;

            start++;
            end--;
        }
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- Classic two-pointer technique problem.

- In-place modification avoids extra space.

- Works efficiently for large inputs.