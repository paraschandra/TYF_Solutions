### 05. Armstrong Number

**Problem Statement:** <br/>
Given an integer N, return true it is an Armstrong number otherwise return false.

An Amrstrong number is a number that is equal to the sum of its own digits each raised to the power of the number of digits.

**Example:** <br/>
**Input**: N = 153

**Output**: True

**Explanation**: 13+53+33 = 1 + 125 + 27 = 153

**Code:** 
```cpp
class Solution {
  public:
    bool isArmstrong(int num) {
        // code here
        int k = to_string(num).length();
        int sum = 0;
        int n = num;
        
        while(n > 0){
            int ld = n % 10;
            sum += pow(ld, k); 
            n = n / 10;
        }

        return sum == num ? true : false;
    }
};
```