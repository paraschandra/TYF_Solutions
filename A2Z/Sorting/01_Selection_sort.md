### 01. Selection Sort

**Problem Statement:** <br/>
Given an array of N integers, write a program to implement the Selection sorting algorithm.

**Example:** <br/>
**Input**: N = 6, array[] = {13,46,24,52,20,9}

**Output**: 9,13,20,24,46,52

**Explanation**: After sorting the array is: 9, 13, 20, 24, 46, 52

**Code:** 
```cpp
class Solution {
  public:
    void selectionSort(int arr[], int n) {
        // code here
        for(int i = 0; i < n-1; i++){
            int mini = i;
            for(int j = i+1; j < n; j++){
                if(arr[j] < arr[mini]) {
                    mini = j;
                }
            }
            swap(arr[mini], arr[i]);
        }
    }
};
```