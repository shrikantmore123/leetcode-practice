# 709. To Lower Case (LeetCode 709)

**Difficulty:** Easy

**Topics:** String

**Tags:** Character Manipulation, ASCII, String Traversal

**LeetCode Link:** https://leetcode.com/problems/to-lower-case/

---

### Problem Statement

Given a string `s`, return the string after replacing every uppercase letter with the same lowercase letter.

---

### Example 1:

**Input:** s = "Hello"

**Output:** "hello"

### Example 2:

**Input:** s = "here"

**Output:** "here"

### Example 3:

**Input:** s = "LOVELY"

**Output:** "lovely"

---

### Constraints:

- `1 <= s.length <= 100`

- `s` consists of printable ASCII characters.

---

### Approach (ASCII Conversion)

- Traverse each character of the string.

- If character is uppercase ('A' to 'Z'):

    - Convert using ASCII: ch + 32

- Otherwise, keep it unchanged.

- Build result using StringBuilder.

---

### Code

```java
class Solution {
    public String toLowerCase(String s) {
        StringBuilder sb = new StringBuilder();

        for(int i = 0; i < s.length(); i++) {
            char ch = s.charAt(i);

            if(65 <= ch && ch <= 90) {
                sb.append((char)(ch + 32));
            } else {
                sb.append(ch);
            }
        }

        return sb.toString();
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(n)`

---

### Notes

- Uses ASCII values for conversion (A=65, a=97).

- Difference between uppercase and lowercase is 32.

- Avoids using built-in toLowerCase() method.