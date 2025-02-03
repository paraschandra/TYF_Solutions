### 21. Next Permutation

**Problem Statement:** <br/>
A permutation of an array of integers is an arrangement of its members into a sequence or linear order.

For example, for arr = [1,2,3], the following are all the permutations of arr: [1,2,3], [1,3,2], [2, 1, 3], [2, 3, 1], [3,1,2], [3,2,1].

**Example:** <br/>
**Input**: nums = [1,2,3]

**Output**: [1,3,2]


**Code:** <br/>
```cpp
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        int n = nums.size();
        int idx = -1;
        for(int i = n-2; i >= 0; i--){
            if(nums[i] < nums[i+1]){
                idx = i;
                break;
            }
        }
        if(idx == -1) {
            reverse(nums.begin(), nums.end());
            return;
        }

        for(int i = n-1; i > idx; i--){
            if(nums[i] > nums[idx]){
                swap(nums[i], nums[idx]);
                break;
            }   
        }

        reverse(nums.begin()+idx+1, nums.end());
        return;
    }
};
```