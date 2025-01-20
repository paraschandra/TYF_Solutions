### Factorial upto n

**Problem Statement:** <br/>
A number n is called a factorial number if it is the factorial of a positive integer. 
For example, the first few factorial numbers are 1, 2, 6, 24, 120,

Given a number n, the task is to return the list/vector of the factorial numbers smaller than or equal to n.

**Example:** <br/>
**Input**: n = 3

**Output**: 1 2

**Explanation**: The first factorial number is 1 which is less than equal to n. The second number is 2 which is less than equal to n,but the third factorial number is 6 which is greater than n. So we print only 1 and 2.

**Code:** 
```cpp
class Solution {
  public:
    long long fact(long long n){
        if(n == 1)
            return 1;
        return n * fact(n-1);
    }
    
    vector<long long> factorialNumbers(long long n) {
        // Write Your Code here
        vector<long long> ans;
        for(int i=1; i<=n; i++){
            long long val = fact(i);
            if(val > n)
                break;
            ans.push_back(val);
        }
        return ans;
    }
};
```