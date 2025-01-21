### 03. Reverse an Array

**Problem Statement:** <br/>
You are given an array of integers arr[]. Your task is to reverse the given array.

`Note`: Modify the array in place.

**Example:** <br/>
**Input**: arr = [1, 4, 3, 2, 6, 5]

**Output**: [5, 6, 2, 3, 4, 1]

**Code:** 
```cpp
class Solution {
  public:
    void reverse(vector<int> &arr, int s, int e){
        if(s < e){
            swap(arr[s], arr[e]);
            reverse(arr, s+1, e-1);
        }
    }
    
    void reverseArray(vector<int> &arr) {
        // code here
        int s = 0, e = arr.size()-1;
        reverse(arr, s, e);
    }
};
```