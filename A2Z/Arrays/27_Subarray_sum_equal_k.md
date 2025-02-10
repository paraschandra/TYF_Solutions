### Lecture_27: Subarray Sum Equal K

**Problem Statement:** <br/>
Given an array of integers nums and an integer k, return the total number of subarrays whose sum equals to k.

A subarray is a contiguous non-empty sequence of elements within an array.

**Example:** <br/>
**Input**: nums = [1,1,1], k = 2

**Output**: 2


**Code:** <br/>
```cpp
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        int n = nums.size();
        map<int, int> mp;
        int preSum = 0, cnt = 0;
        mp[0] = 1;

        for(int i = 0; i < n; i++){
            preSum += nums[i];
            int rem = preSum - k;
            cnt += mp[rem];
            mp[preSum] += 1;
        }
        return cnt;
    }
};
```