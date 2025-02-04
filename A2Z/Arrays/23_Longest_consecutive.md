### 23. Longest Consecutive Sequence

**Problem Statement:** <br/>
Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.

You must write an algorithm that runs in O(n) time.

**Example:** <br/>
**Input**: nums = [100,4,200,1,3,2]

**Output**: 4

**Explanation**: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.


**Code:** <br/>
```cpp
// Sorting: O(NlogN)
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        int n = nums.size();
        if(n == 0) return 0;

        sort(nums.begin(), nums.end());
        int ans = 0, mx = 1;

        for(int i = 1; i < n; i++){
            // imp. condition to check for repeating elements
            if(nums[i] != nums[i-1]){
                if(nums[i] == nums[i-1] + 1){
                    mx++;
                } else {
                    ans = max(ans, mx);
                    mx = 1;
                }
            }
        }
        return max(ans, mx);
    }
};

// using set: O(n)
class Solution {
public:
    int longestConsecutive(vector<int>& nums) {
        int n = nums.size();
        if(n == 0) return 0;

        int ans = 1;
        unordered_set<int> s;

        for(auto i: nums)
            s.insert(i);
        
        for(auto i: s){
            if(s.find(i-1) == s.end()){
                int cnt = 1, x = i;
                while(s.find(x+1) != s.end()){
                    x++;
                    cnt++;
                }
                ans = max(ans, cnt);
            }
        }
        return ans;
    }
};
```