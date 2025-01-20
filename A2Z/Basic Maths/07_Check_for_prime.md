### Check for Prime

**Problem Statement:** <br/>
Given an integer N, check whether it is prime or not. A prime number is a number that is only divisible by 1 and itself and the total number of divisors is 2.

**Example:** <br/>
**Input**: N =10

**Output**: False

**Explanation**: 10 is not prime, it is a composite number because it has 4 divisors: 1, 2, 5 and 10.

**Code:** 
```cpp
class Solution {
  public:
    int checkPrime(int n) {
        // Write Your Code here
        int cnt = 0;

        for(int i = 1; i <= sqrt(n); i++){
            if(n % i == 0){
                cnt++;
            }
            if(n / i != i){
                cnt++;
            }
        }

        return (cnt == 2) ? true : false;
    }
};
```