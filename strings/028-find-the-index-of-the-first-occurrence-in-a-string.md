# 28. Find the Index of the First Occurrence in a String (LeetCode 28)

**Difficulty:** Easy

**Topics:** String, Two Pointers

**Tags:** String Matching, Brute Force, Sliding Window

**LeetCode Link:** https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/

---

### Problem Statement

Given two strings `needle` and `haystack`, return the index of the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part of `haystack`.

---

### Example 1:

**Input:** haystack = "sadbutsad", needle = "sad"

**Output:** 0

**Explanation:** "sad" occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.

### Example 2:

**Input:** haystack = "leetcode", needle = "leeto"

**Output:** -1

**Explanation:** "leeto" did not occur in "leetcode", so we return -1.

---

### Constraints:

- `1 <= haystack.length, needle.length <= 10⁴`

- Only lowercase English letters

---

### Approach (Brute Force String Matching)

- Traverse haystack from index 0 to n - m.

- For each index:

    - Compare characters of needle one by one.

- If all characters match → return index.

- If no match found → return -1.

---

### Code

```java
class Solution {
    public int strStr(String haystack, String needle) {
        int haystackLength = haystack.length();
        int needleLength = needle.length();

        if(haystackLength < needleLength) {
            return -1;
        }

        for(int i = 0; i <= haystackLength - needleLength; i++) {
            int j = 0;

            while(j < needleLength && haystack.charAt(i + j) == needle.charAt(j)) {
                j++;
            }

            if(j == needleLength) {
                return i;
            }
        }

        return -1;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n * m)`

- Space Complexity: `o(1)`

---

### Notes

- Simple brute-force approach for substring search.

- Works well for small inputs.

- Optimal solutions use KMP algorithm (o(n + m)).