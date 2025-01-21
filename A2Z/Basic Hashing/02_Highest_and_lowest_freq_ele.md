### 02. Find the highest/lowest frequency element

**Problem Statement:** <br/>
Given an array of size N. Find the highest and lowest frequency element.

**Example:** <br/>
**Input**: array[] = {10,5,10,15,10,5}

**Output**: 10 15

**Explanation**: The frequency of 10 is 3, i.e. the highest and the frequency of 15 is 1 i.e. the lowest.


**Code:** 
```cpp
class Solution {
  public:
    // Function to count the frequency of all elements from 1 to N in the array.
    vector<int> countFreq(int arr[], int n) {
        // code here
        unordered_map<int, int> map;
        for (int i = 0; i < n; i++)
            map[arr[i]]++;

        int maxFreq = 0, minFreq = n;
        int maxEle = 0, minEle = 0;
        
        for (auto it : map) {
            int count = it.second;
            int element = it.first;

            if (count > maxFreq) {
                maxEle = element;
                maxFreq = count;
            }
            if (count < minFreq) {
                minEle = element;
                minFreq = count;
            }
        }

        return {minEle, maxEle};
    }
};
```