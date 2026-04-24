# 1154. Day of the Year (LeetCode 1154)

**Difficulty:** Easy

**Topics:** String, Math

**Tags:** Date Calculation, Leap Year, Parsing

**LeetCode Link:** https://leetcode.com/problems/day-of-the-year/

---

### Problem Statement

Given a string `date` representing a Gregorian calendar date formatted as `YYYY-MM-DD`, return the day number of the year.

---

### Example 1:

**Input:** date = "2019-01-09"

**Output:** 9

**Explanation:** Given date is the 9th day of the year in 2019.

### Example 2:

**Input:** date = "2019-02-10"

**Output:** 41

---

### Constraints:

- `date.length == 10`

- `date[4] == date[7] == '-'`, and all other `date[i]`'s are digits

- `date` represents a calendar date between Jan 1st, 1900 and Dec 31st, 2019.

---

### Approach (Date Parsing + Prefix Days)

- Split date into `year`, `month` and `day`.

- Use a predefined array storing cumulative days before each month.

- Add current day to cumulative days.

- If leap year and month > 2 → add 1 extra day.

---

### Code

```java
class Solution {
    public int dayOfYear(String date) {
        String splittedDate[] = date.split("-");

        int year = Integer.parseInt(splittedDate[0]);
        int month = Integer.parseInt(splittedDate[1]);
        int day = Integer.parseInt(splittedDate[2]);

        int daysBeforeMonth[] = {0, 31, 59, 90, 120, 151, 181, 212, 243, 273, 304, 334};

        int totalDays = daysBeforeMonth[month - 1] + day;
        
        if(year % 4 == 0 && year % 100 != 0 || year % 400 == 0) {
            if(month > 2) {
                totalDays += 1;
            }
        }

        return totalDays;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(1)`

- Space Complexity: `o(1)`

---

### Notes

- Leap year condition:
    
    - divisible by 4 and not by 100

    - OR divisible by 400

- Precomputed days array simplifies calculation.

- Efficient constant-time solution.