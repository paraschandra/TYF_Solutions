### 08. Find the Union

**Problem Statement:** <br/>
Given two sorted arrays, arr1, and arr2 of size n and m. Find the union of two sorted arrays.

The union of two arrays can be defined as the common and distinct elements in the two arrays.NOTE: Elements in the union should be in ascending order.

**Example:** <br/>
**Input**: <br/>
n = 5,m = 5. <br/>
arr1[] = {1,2,3,4,5}<br/>
arr2[] = {2,3,4,4,5}

**Output**: {1,2,3,4,5}

**Code:** <br/>
```cpp
class Solution {
  public:
    // a,b : the arrays
    // Function to return a list containing the union of the two arrays.
    vector<int> findUnion(vector<int> &arr1, vector<int> &arr2) {
        // Your code here
        // return vector with correct order of elements
        int n = arr1.size(), m = arr2.size();
        vector<int> ans;
        int l = 0, r = 0;
        
        while(l<n && r<m){
            if(arr1[l] <= arr2[r]){
                if(ans.size() == 0 || ans.back() != arr1[l])
                    ans.push_back(arr1[l]);
                l++;
            } else{
                if(ans.size() == 0 || ans.back() != arr2[r])
                    ans.push_back(arr2[r]);
                r++;
            }
        }
        
        while(l<n){
            if(arr1[l] != ans.back()){
                ans.push_back(arr1[l]);
            }
            l++;
        }
        
        while(r<m){
            if(arr2[r] != ans.back()){
                ans.push_back(arr2[r]);
            }
            r++;
        }
        
        return ans;
    }
};
```