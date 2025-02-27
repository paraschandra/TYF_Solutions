### 19. Best Time to Buy and Sell Stock

**Problem Statement:** <br/>
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

**Example:** <br/>
**Input**: prices = [7,1,5,3,6,4]

**Output**: 5

**Explanation**: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.


**Code:** <br/>
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int l = 0, r = 0;
        int ans = 0;

        while(r < prices.size()) {
            if(prices[l] < prices[r]){
                ans = max(ans, prices[r] - prices[l]);
            } else {
                l = r;
            }
            r++;
        }
        return ans;
    }
};
```