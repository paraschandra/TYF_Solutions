### 12. Longest Subarray with given Sum K(Positives)

**Problem Statement:** <br/>
Given an array and a sum k, we need to print the length of the longest subarray that sums to k.

**Example:** <br/>
**Input**: N = 3, k = 5, array[] = {2,3,5}

**Result**: 2

**Explanation**: The longest subarray with sum 5 is {2, 3}. And its length is 2.


**Code:** <br/>
```cpp
class Solution {
  public:
    int longestSubarray(vector<int>& arr, int k) {
        // code here
        int n = arr.size();
        int sum = arr[0];
        int l = 0, r = 0;
        int maxLen = 0;
        
        while(r < n) {
            while(l <= r and sum > k) {
                sum -= arr[l];
                l++;
            }
            
            if(sum == k) {
                maxLen = max(maxLen, r-l+1);
            }
            
            r++;
            if(r < n) sum += arr[r];
        }
        return maxLen;
    }
};
```