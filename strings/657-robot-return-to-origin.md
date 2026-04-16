# 657. Robot Return to Origin (LeetCode 657)

**Difficulty:** Easy

**Topics:** String, Simulation

**Tags:** Simulation, Coordinate Tracking, String Traversal

**LeetCode Link:** https://leetcode.com/problems/robot-return-to-origin/

---

### Problem Statement

There is a robot starting at the position `(0, 0)`, the origin, on a 2D plane. Given a sequence of its moves, judge if this robot ends up at `(0, 0)` after it completes its moves.

You are given a string `moves` that represents the move sequence of the robot where `moves[i]` represents its ith move. Valid moves are `'R'` (right), `'L'` (left), `'U'` (up), and `'D'` (down).

Return `true` if the robot returns to the origin after it finishes all of its moves, or `false` otherwise.

Note: The way that the robot is "facing" is irrelevant. `'R'` will always make the robot move to the right once, `'L'` will always make it move left, etc. Also, assume that the magnitude of the robot's movement is the same for each move.

---

### Example 1:

**Input:** moves = "UD"

**Output:** true

**Explanation:** The robot moves up once, and then down once. All moves have the same magnitude, so it ended up at the origin where it started. Therefore, we return true.

### Example 2:

**Input:** moves = "LL"

**Output:** false

**Explanation:** The robot moves left twice. It ends up two "moves" to the left of the origin. We return false because it is not at the origin at the end of its moves.

### Example 3:

**Input:** s = " "

**Output:** true

**Explanation:** s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

---

### Constraints:

- `1 <= moves.length <= 2 * 10⁴`

- `moves` only contains the characters `'U'`, `'D'`, `'L'` and `'R'`.

---

### Approach (Coordinate Simulation)

- Start from (x, y) = (0, 0).

- Traverse each move:

    - 'U' → y++

    - 'D' → y--

    - 'R' → x++

    - 'L' → x--

- After processing all moves:

    - If (x == 0 && y == 0) → return true

    - Else → return false

---

### Code

```java
class Solution {
    public boolean judgeCircle(String moves) {
        int x = 0, y = 0;

        for(int i = 0; i < moves.length(); i++) {
            char move = moves.charAt(i);

            if(move == 'U') {
                y++;
            } else if(move == 'D') {
                y--;
            } else if(move == 'R') {
                x++;
            } else {
                x--;
            }
        }

        return x == 0 && y == 0;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- Simple simulation problem using coordinates.

- No extra space required.

- Good beginner problem for understanding movement tracking.

- Can also be solved using counting approach.