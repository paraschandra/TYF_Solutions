### 11. Single Number

**Problem Statement:** <br/>
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

**Example:** <br/>
**Input**: nums = [2,2,1]

**Output**: 1


**Code:** <br/>
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int ans = 0;
        for(auto i: nums){
            ans ^= i;
        }
        return ans;
    }
};
```