### Sum of first n terms

**Problem Statement:** <br/>
Given an integer n, calculate the sum of series 1<sup>3</sup> + 2<sup>3</sup> + 3<sup>3</sup> + 4<sup>3</sup> + … till n-th term.

**Example:** <br/>
**Input**: n = 5

**Output**: 225

**Code:** 
```cpp
class Solution {
  public:
    int sumOfSeries(int n) {
        // code here
        if(n == 1)
            return 1;
        
        return (n*n*n) + sumOfSeries(n-1);
    }
};
```