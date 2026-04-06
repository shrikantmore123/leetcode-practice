# 121. Best Time to Buy and Sell Stock (LeetCode 121)

**Difficulty:** Easy

**Topics:** Array

**Tags:** Greedy, Single Pass, Profit Calculation


**LeetCode Link:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

---

### Problem Statement

You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If no profit is possible, return `0`.

---

### Example 1:

**Input:** prices = [7,1,5,3,6,4]

**Output:** 5

**Explanation:** Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

### Example 2:

**Input:** prices = [7,6,4,3,1]

**Output:** 0

**Explanation:** In this case, no transactions are done and the max profit = 0.

---

### Constraints:

- `1 <= prices.length <= 10⁵`

- `0 <= prices[i] <= 10⁴`

---

### Approach (Greedy / Single Pass)

- Track the minimum price (buyPrice) seen so far.

- For each day:
    
    - If current price is higher → calculate profit.
    
    - Update maximum profit if needed.
    
    - Otherwise → update buyPrice.

- Only one pass through the array.

---

### Code

```java
class Solution {
    public int maxProfit(int[] prices) {
        int buyPrice = Integer.MAX_VALUE;
        int maxProfit = 0;

        for(int i = 0; i < prices.length; i++) {
            if(buyPrice < prices[i]) {   // profit
                int profit = prices[i] - buyPrice;   // today's profit
                maxProfit = Math.max(maxProfit, profit);
            } else {
                buyPrice = prices[i];
            }
        }

        return maxProfit;
    }
}
```

---

### Time & Space Complexity

- Time Complexity: `o(n)`

- Space Complexity: `o(1)`

---

### Notes

- This is a classic greedy problem.

- Always try to buy at the lowest price before selling.