### 10. Max Consecutive Ones

**Problem Statement:** <br/>
Given a binary array nums, return the maximum number of consecutive 1's in the array.

**Example:** <br/>
**Input**: nums = [1,0,1,1,0,1]

**Output**: 2


**Code:** <br/>
```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int mx = 0, ans = 0;
        for(auto i: nums){
            if(i == 1) {
                mx++;
            } else {
                ans = max(ans, mx);
                mx = 0;
            }
        }
        return max(ans, mx);
    }
};
```