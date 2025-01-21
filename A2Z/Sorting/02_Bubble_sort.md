### 02. Bubble Sort

**Problem Statement:** <br/>
Given an array of N integers, write a program to implement the Bubble Sorting algorithm.

**Example:** <br/>
**Input**: N = 6, array[] = {13,46,24,52,20,9}

**Output**: 9,13,20,24,46,52

**Explanation**: After sorting the array is: 9, 13, 20, 24, 46, 52

**Code:** 
```cpp
class Solution {
  public:
    void bubbleSort(int arr[], int n) {
        // code here
        for (int i = n - 1; i >= 0; i--) {
            for (int j = 0; j <= i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    swap(arr[j+1], arr[j]);
                }
            }
        }
    }
};
```