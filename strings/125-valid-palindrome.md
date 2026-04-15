# 125. Valid Palindrome (LeetCode 125)

**Difficulty:** Easy

**Topics:** String, Two Pointers

**Tags:** String Processing, Two Pointers, Palindrome Check

**LeetCode Link:** https://leetcode.com/problems/valid-palindrome/

---

### Problem Statement

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` if it is a palindrome, or `false` otherwise.

---

### Example 1:

**Input:** s = "A man, a plan, a canal: Panama"

**Output:** true

**Explanation:** "amanaplanacanalpanama" is a palindrome.

### Example 2:

**Input:** s = "race a car"

**Output:** false

**Explanation:** "raceacar" is not a palindrome.

### Example 3:

**Input:** s = " "

**Output:** true

**Explanation:** s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

---

### Constraints:

- `1 <= s.length <= 2 * 10⁵`

- `s` consists only of printable ASCII characters.

---

### Approach (String Cleaning + Two Pointer Check)

- CRemove all non-alphanumeric characters using regex.

- Convert string to lowercase.

- Compare characters from both ends moving inward.

- If mismatch found → return false.

---

### Code

```java
class Solution {
    public boolean isPalindrome(String s) {
        s = s.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();

        for(int i = 0; i < s.length() / 2; i++) {
            if(s.charAt(i) != s.charAt(s.length() - 1 - i)) {
                return false;
            }
        }

        return true;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(n)`

---

### Notes

- Regex simplifies removal of unwanted characters.

- Uses extra space due to new processed string.

- Alternative approach: two pointers without extra space.