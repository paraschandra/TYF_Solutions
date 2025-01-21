### 01. Largest Element in an Array

**Problem Statement:** <br/>
Given an array arr[]. The task is to find the largest element and return it.

**Example:** <br/>
**Input**: arr[] = [1, 8, 7, 56, 90]

**Output**: 90

**Explanation**: The largest element of the given array is 90.

**Code:** <br/>
```cpp
class Solution {
  public:
    int largest(vector<int> &arr) {
        // code here
        int max = INT_MIN;
        
        for (auto i: arr) {
            if (i > max)
                max = i;
        }
        
        return max;
    }
};
```