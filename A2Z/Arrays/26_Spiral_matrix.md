### Lecture_26: Spiral Matrix

**Problem Statement:** <br/>
Given an m x n matrix, return all elements of the matrix in spiral order.

**Example:** <br/>
**Input**: matrix = [[1,2,3],[4,5,6],[7,8,9]]

**Output**: [1,2,3,6,9,8,7,4,5]


**Code:** <br/>
```cpp
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        vector<int> ans;
        int n = matrix.size(), m = matrix[0].size();
        int top = 0, left = 0, bottom = n-1, right = m-1;

        while(top <= bottom && left <= right){
            for(int i = left; i <= right; i++){
                ans.push_back(matrix[top][i]);
            }
            top++;
            for(int i = top; i <= bottom; i++){
                ans.push_back(matrix[i][right]);
            }
            right--;
            
            if(top <= bottom){
                for(int i = right; i >= left; i--){
                    ans.push_back(matrix[bottom][i]);
                }
                bottom--;
            }
            if(left <= right){
                for(int i = bottom; i >= top; i--){
                    ans.push_back(matrix[i][left]);
                }
                left++;
            }
        }
        return ans;
    }
};
```