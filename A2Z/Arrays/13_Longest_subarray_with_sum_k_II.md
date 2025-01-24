### 13. Longest Subarray with Sum K

**Problem Statement:** <br/>
Given an array arr[] containing integers and an integer k, your task is to find the length of the longest subarray where the sum of its elements is equal to the given value k. If there is no subarray with sum equal to k, return 0.

**Example:** <br/>
**Input**: arr[] = [10, 5, 2, 7, 1, -10], k = 15

**Output**: 6

**Explanation**: Subarrays with sum = 15 are [5, 2, 7, 1], [10, 5] and [10, 5, 2, 7, 1, -10]. The length of the longest subarray with a sum of 15 is 6.


**Code:** <br/>
```cpp
class Solution{
    public:
    int lenOfLongSubarr(int A[],  int N, int K) 
    { 
        // Complete the function
        map<long long, int> preSum;
        long long sum = 0;
        int maxLen = 0;
        
        for(int i=0; i<N; i++){
            sum += A[i];
            if(sum == K){
                maxLen = max(maxLen, i+1);
            }
            
            long long rem = sum-K;
            if(preSum.find(rem) != preSum.end()){
                int len = i-preSum[rem];
                maxLen = max(maxLen, len);
            }
            if(preSum.find(sum) == preSum.end()){
                preSum[sum] = i;
            }
        }
        return maxLen;
    } 

};
```