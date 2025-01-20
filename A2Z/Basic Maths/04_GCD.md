### 04. GCD or HCF

**Problem Statement:** <br/>
Given two integers a and b, write a function lcmAndGcd() to compute their LCM and GCD. The function inputs two integers a and b and returns a list containing their LCM and GCD.

**Example:** <br/>
**Input**: a = 5 , b = 10

**Output**: [10, 5]

**Explanation**: LCM of 5 and 10 is 10, while their GCD is 5.

**Code:** 
```cpp
class Solution {
  public:
    vector<int> lcmAndGcd(int a, int b) {
        // code here
        int x = a, y = b;
        while(b != 0){
            int rem = a % b;
            a = b;
            b = rem;
        }
        
        int gcd = a;
        int lcm = (x*y) / gcd;
        
        return {lcm, gcd};
    }
};
```