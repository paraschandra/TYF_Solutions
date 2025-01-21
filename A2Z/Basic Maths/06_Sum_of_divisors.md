### 06. Sum 1 to n Divisors

**Problem Statement:** <br/>
Given a positive integer n, The task is to find the value of Σi F(i) where i is from 1 to n and function F(i) is defined as the sum of all divisors of i.

**Example:** <br/>
**Input**: n = 4

**Output**: 15

**Explanation**:
F(1) = 1 <br>
F(2) = 1 + 2 = 3 <br>
F(3) = 1 + 3 = 4 <br>
F(4) = 1 + 2 + 4 = 7 <br>
So, F(1) + F(2) + F(3) + F(4) = 1 + 3 + 4 + 7 = 15

**Code:** 
```cpp
class Solution {
  public:
    int sumOfDivisors(int n) {
        // Write Your Code here
        int sum = 0;
        
        for(int i = 1; i <= n; i++){
            sum += i*(n/i);
        }
        
        return sum;
    }
};
```