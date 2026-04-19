# 151. Reverse Words in a String (LeetCode 151)

**Difficulty:** Medium

**Topics:** String

**Tags:** String Manipulation, Splitting, Reverse Traversal

**LeetCode Link:** https://leetcode.com/problems/reverse-words-in-a-string/

---

### Problem Statement

Given an input string `s`, reverse the order of the words.

A word is defined as a sequence of non-space characters. The words in `s` will be separated by at least one space.

Return a string of the words in reverse order concatenated by a single space.

Note that `s` may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

 

---

### Example 1:

**Input:** s = "the sky is blue"

**Output:** "blue is sky the"

### Example 2:

**Input:** s = "  hello world  "

**Output:** "world hello"

**Explanation:** Your reversed string should not contain leading or trailing spaces.

### Example 3:

**Input:** s = "a good   example"

**Output:** "example good a"

**Explanation:** You need to reduce multiple spaces between two words to a single space in the reversed string.

---

### Constraints:

- `1 <= s.length <= 10⁴`

- `s` contains English letters (upper-case and lower-case), digits, and spaces `' '`.

- There is at least one word in `s`.

---

### Approach (Split + Reverse)

- Split the string using regex `"\\s+"` to handle multiple spaces.

- Traverse the array in reverse order.

- Append words to `StringBuilder`.

- Remove trailing space using `.stripTrailing()`.
---

### Code

```java
class Solution {
    public String reverseWords(String s) {
        String strArr[] = s.split("\\s+");
        StringBuilder sb = new StringBuilder();

        for(int i = strArr.length - 1; i >= 0; i--) {
            sb.append(strArr[i] + " ");
        }

        return sb.toString().stripTrailing();
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(n)`

---

### Notes

- Regex `"\\s+"` handles multiple spaces efficiently.

- Uses extra space due to split and StringBuilder.

- Easy and readable solution.