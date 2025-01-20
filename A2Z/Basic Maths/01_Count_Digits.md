### 01. Count Digits

**Problem Statement:** <br/>
Given a positive integer n, count the number of digits in n that divide n evenly (i.e., without leaving a remainder). Return the total number of such digits.

A digit d of n divides n evenly if the remainder when n is divided by d is 0 (n % d == 0).
Digits of n should be checked individually. If a digit is 0, it should be ignored because division by 0 is undefined.

**Example:** <br/>
**Input**: n = 12

**Output**: 2

**Explanation**: 1, 2 when both divide 12 leaves remainder 0.

**Code:** <br/>
```cpp
class Solution {
  public:
    // Function to count the number of digits in n that evenly divide n
    int evenlyDivides(int n) {
        // code here
        int ans = 0, x = n;
        
        while(n != 0) {
            int d = n % 10;
            if(d == 0) {
                n /= 10;
                continue;
            }
            if(x % d == 0)
                ans++;
            n /= 10;
        }
        
        return ans;
    }
};
```