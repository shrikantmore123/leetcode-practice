# 67. Add Binary (LeetCode 67)

**Difficulty:** Easy

**Topics:** String, Bit Manipulation

**Tags:** Binary Addition, Two Pointers, Carry Handling

**LeetCode Link:** https://leetcode.com/problems/add-binary/

---

### Problem Statement

Given two binary strings `a` and `b`, return their sum as a binary string.

---

### Example 1:

**Input:** a = "11", b = "1"

**Output:** "100"

### Example 2:

**Input:** a = "1010", b = "1011"

**Output:** "10101"

---

### Constraints:

- `1 <= a.length, b.length <= 10⁴`

- `a` and `b` consist only of `'0'` or `'1'` characters.

- Each string does not contain leading zeros except for the zero itself.

---

### Approach (Binary Addition with Carry)

- Start from the end of both strings.

- Maintain a `carry`.

- Add digits from both strings and carry.

- Append `(sum % 2)` to result.

- Update carry `(sum / 2)`.

- Reverse result at the end.

---

### Code

```java
class Solution {
    public String addBinary(String a, String b) {
        StringBuilder result = new StringBuilder();
        int i = a.length() - 1;
        int j = b.length() - 1;
        int carry = 0;

        while(i >= 0 || j >= 0 || carry == 1) {
            int sum = carry;
            
            if(i >= 0) {
                sum += a.charAt(i--) - '0';
            }
            
            if(j >= 0) {
                sum += b.charAt(j--) - '0';
            }

            result.append(sum % 2);
            carry = sum / 2;
        }
        
        return result.reverse().toString();
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(max(n, m))`

- Space Complexity: `o(max(n, m))`

---

### Notes

- Similar to manual binary addition.

- Uses StringBuilder for efficiency.

- Handles different lengths and carry properly.

- Classic bit manipulation problem.