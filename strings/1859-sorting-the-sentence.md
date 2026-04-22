# 1859. Sorting the Sentence (LeetCode 1859)

**Difficulty:** Easy

**Topics:** String, Array

**Tags:** String Manipulation, Index Mapping, Reconstruction

**LeetCode Link:** https://leetcode.com/problems/sorting-the-sentence/

---

### Problem Statement

A sentence is a list of words that are separated by a single space with no leading or trailing spaces. Each word consists of lowercase and uppercase English letters.

A sentence can be shuffled by appending the 1-indexed word position to each word then rearranging the words in the sentence.

- For example, the sentence `"This is a sentence"` can be shuffled as `"sentence4 a3 is2 This1"` or `"is2 sentence4 This1 a3"`.

Given a shuffled sentence `s` containing no more than `9` words, reconstruct and return the original sentence.

---

### Example 1:

**Input:** s = "is2 sentence4 This1 a3"

**Output:** "This is a sentence"

**Explanation:** Sort the words in s to their original positions "This1 is2 a3 sentence4", then remove the numbers.

### Example 2:

**Input:** s = "Myself2 Me1 I4 and3"

**Output:** "Me Myself and I"

**Explanation:** Sort the words in s to their original positions "Me1 Myself2 and3 I4", then remove the numbers.

---

### Constraints:

- `2 <= s.length <= 200`

- `s` consists of lowercase and uppercase English letters, spaces, and digits from `1` to `9`.

- The number of words in `s` is between `1` and `9`.

- The words in `s` are separated by a single space.

- `s` contains no leading or trailing spaces.

---

### Approach (Index Mapping using Helper Array)

- Split the string into words.

- Extract the last character (digit) from each word → position.

- Store the word (without digit) in correct index of helper array.

- Build final string using helper array.

---

### Code

```java
class Solution {
    public String sortSentence(String s) {
        String splitedArr[] = s.split(" ");
        String helperArr[] = new String[splitedArr.length];

        StringBuilder sb = new StringBuilder();

        for(int i = 0;  i < splitedArr.length; i++) {
            int idx = splitedArr[i].charAt(splitedArr[i].length() - 1) - '0';
            helperArr[idx - 1] = splitedArr[i].substring(0, splitedArr[i].length() - 1);
        }

        for(int i = 0; i < helperArr.length; i++) {
            sb.append(helperArr[i]).append(" ");
        }

        return sb.toString().trim();
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(n)`

---

### Notes

- Uses extra array for correct placement of words.

- Digit extraction using ASCII conversion (`- '0'`).

- StringBuilder helps efficient concatenation.

- Simple and clean reconstruction approach.