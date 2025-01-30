### 17. Maximum Subarray

**Problem Statement:** <br/>
Given an integer array nums, find the subarray with the largest sum, and return its sum.

**Example:** <br/>
**Input**: nums = [-2,1,-3,4,-1,2,1,-5,4]

**Output**: 6

**Explanation**: The subarray [4,-1,2,1] has the largest sum 6.


**Code:** <br/>
```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int ans = INT_MIN, mx = 0;
        for(auto i: nums){
            mx += i;
            ans = max(ans, mx);
            if(mx < 0)
                mx = 0;
        }
        return ans;
    }
};
```