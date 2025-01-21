### 05. Recursive Bubble Sort

**Problem Statement:** <br/>
Given an array of N integers, write a program to implement the Recursive Bubble Sort algorithm.

**Example:** <br/>
**Input**: N = 6, array[] = {13,46,24,52,20,9}

**Output**: 9,13,20,24,46,52

**Explanation**: After sorting the array is: 9, 13, 20, 24, 46, 52

**Code:** 
```cpp
class Solution {
  public:
    void bubble_sort(int arr[], int n) {
        if (n == 1) return;

        for (int j = 0; j <= n - 2; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j+1], arr[j]);
            }
        }
        bubble_sort(arr, n - 1);
    }
};
```