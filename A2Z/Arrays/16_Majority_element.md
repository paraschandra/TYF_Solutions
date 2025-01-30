### 16. Majority Element

**Problem Statement:** <br/>
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

**Example:** <br/>
**Input**: nums = [3,2,3]

**Output**: 3


**Code:** <br/>
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int cnt = 0, ele;
        for(int i = 0; i < nums.size(); i++){
            if(cnt == 0){
                ele = nums[i];
                cnt++;
            } else if(nums[i] == ele){
                cnt++;
            } else {
                cnt--;
            }
        }

        int c = 0;
        for(int i = 0; i < nums.size(); i++){
            if(nums[i] == ele){
                c++;
            }
        }

        if(c >= nums.size()/2){
            return ele;
        } else {
            return -1;
        }
    }
};
```