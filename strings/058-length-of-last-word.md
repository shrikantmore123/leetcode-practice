# 58. Length of Last Word (LeetCode 58)

**Difficulty:** Easy

**Topics:** String

**Tags:** String Traversal, Two Pointers, Reverse Traversal

**LeetCode Link:** https://leetcode.com/problems/length-of-last-word/

---

### Problem Statement

Given a string `s` consisting of words and spaces, return the length of the last word in the string.

A word is a maximal substring consisting of non-space characters only.

---

### Example 1:

**Input:** title = s = "Hello World"

**Output:** 5

**Explanation:** The last word is "World" with length 5.

### Example 2:

**Input:** title = s = "   fly me   to   the moon  "

**Output:** 4

**Explanation:** The last word is "moon" with length 4.

### Example 3:

**Input:** s = "luffy is still joyboy"

**Output:** 6

**Explanation:** The last word is "joyboy" with length 6.
---

### Constraints:

- `1 <= s.length <= 10⁴`

- `s` consists of only English letters and spaces `' '`.

- There will be at least one word in `s`.

---

### Approach (Reverse Traversal)

- Start from the end of the string.

- Skip all trailing spaces.

- Count characters until a space is found.

- Return the count of last word length.

---

### Code

```java
class Solution {
    public int lengthOfLastWord(String s) {
        int end = s.length() - 1;

        while(end >= 0 && s.charAt(end) == ' ') {
            end--;
        }

        int start = end;
        while(start >= 0 && s.charAt(start) != ' ') {
            start--;
        }

        return end - start;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- Efficient solution without extra space.

- Avoids splitting the string.

- Handles trailing spaces properly.

- Classic reverse traversal pattern.