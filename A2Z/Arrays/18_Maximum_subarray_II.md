### 18. Maximum Subarray II

**Problem Statement:** <br/>
Given an integer array arr, find the contiguous subarray (containing at least one number) which
has the largest sum and returns its sum and prints the subarray.

**Example:** <br/>
**Input**: nums = [-2,1,-3,4,-1,2,1,-5,4]

**Output**: 6

**Explanation**: The subarray [4,-1,2,1] has the largest sum 6.


**Code:** <br/>
```cpp
class Solution {
public:
    long long maxSubarraySum(int arr[], int n) {
        long long maxi = LONG_MIN; // maximum sum
        long long sum = 0;

        int start = 0;
        int ansStart = -1, ansEnd = -1;
        for (int i = 0; i < n; i++) {

            if (sum == 0) start = i; // starting index

            sum += arr[i];

            if (sum > maxi) {
                maxi = sum;

                ansStart = start;
                ansEnd = i;
            }

            if (sum < 0) {
                sum = 0;
            }
        }
        cout << "The subarray is: [";
        for (int i = ansStart; i <= ansEnd; i++) {
            cout << arr[i] << " ";
        }
        cout << "]\n";
        
        return maxi;
    }    
};
```