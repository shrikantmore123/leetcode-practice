# 242. Valid Anagram (LeetCode 242)

**Difficulty:** Easy

**Topics:** String, Sorting

**Tags:** Sorting, Frequency Check, Anagram

**LeetCode Link:** https://leetcode.com/problems/valid-anagram/

---

### Problem Statement

Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.

---

### Example 1:

**Input:** s = "anagram", t = "nagaram"

**Output:** true

### Example 2:

**Input:** s = "rat", t = "car"

**Output:** false

---

### Constraints:

- `1 <= s.length, t.length <= 5 * 10⁴`

- `s` and `t` consist of lowercase English letters.

---

### Approach (Sorting + Comparison)

- If lengths differ → return false.

- Convert both strings to character arrays.

- Sort both arrays.

- Compare arrays using `Arrays.equals()`.

---

### Code

```java
class Solution {
    public boolean isAnagram(String s, String t) {
        if(s.length() != t.length()) {
            return false;
        }

        char sCharArr[] = s.toCharArray();
        char tCharArr[] = t.toCharArray();

        Arrays.sort(sCharArr);
        Arrays.sort(tCharArr);

        return Arrays.equals(sCharArr, tCharArr);
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n log n)`

- Space Complexity: `o(n)`

---

### Notes

- Sorting ensures same characters align in order.

- Works well for small inputs.

- Optimal solution uses frequency array → `o(n)` time.