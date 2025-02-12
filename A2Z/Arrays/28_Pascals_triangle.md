### Lecture_28: Pascal's Triangle

**Problem Statement:** <br/>
Given an integer numRows, return the first numRows of Pascal's triangle.

**Example:** <br/>
**Input**: numRows = 5

**Output**: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]


**Code:** <br/>
```cpp
// TC: O(n3)
class Solution {
public:
    int nCr(int n, int r) {
        long long res = 1;

        for(int i = 0; i < r; i++){
            res = res*(n-i) / (i+1);
        }
        return (int) res;
    }

    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ans;
        
        for(int r = 1; r <= numRows; r++){
            vector<int> tmp;
            for(int c = 1; c <= r; c++){
                tmp.push_back(nCr(r-1, c-1));
            }
            ans.push_back(tmp);
        }
        return ans;
    }
};

// TC: O(n2)
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ans;
        for(int n = 0; n < numRows; n++){
            vector<int> row;
            row.push_back(1);
            int val = 1;
            for(int k = 1; k <= n; k++){
                val = val * (n-k+1) / k;
                row.push_back(val);
            }
            ans.push_back(row);
        }
        return ans;
    }
};
```