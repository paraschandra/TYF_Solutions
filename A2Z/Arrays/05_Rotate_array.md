### 05. Rotate Array

**Problem Statement:** <br/>
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

**Example:** <br/>
**Input**: nums = [1,2,3,4,5,6,7], k = 3

**Output**: [5,6,7,1,2,3,4]

**Explanation**:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]


**Code:** <br/>
```cpp
class Solution {
public:
    void reverse(vector<int> &nums, int s, int e) {
        while(s <= e) {
            swap(nums[s], nums[e]);
            s++;
            e--;
        }
    }

    void rotate(vector<int>& nums, int k) {
        int n = nums.size();
        k = k % n;
        reverse(nums, 0, n-1);
        reverse(nums, 0, k-1);
        reverse(nums, k, n-1);
    }
};
```