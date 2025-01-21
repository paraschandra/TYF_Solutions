### 06. Recursive Insertion Sort

**Problem Statement:** <br/>
Given an array of N integers, write a program to implement the Recursive Insertion Sort algorithm.

**Example:** <br/>
**Input**: N = 6, array[] = {13,46,24,52,20,9}

**Output**: 9,13,20,24,46,52

**Explanation**: After sorting the array is: 9, 13, 20, 24, 46, 52

**Code:** 
```cpp
class Solution {
  public:
    void insertion_sort(int arr[], int n) {
        if (i == n) return;

        int j = i;
        while (j > 0 && arr[j - 1] > arr[j]) {
            int temp = arr[j - 1];
            arr[j - 1] = arr[j];
            arr[j] = temp;
            j--;
        }
        insertion_sort(arr, i + 1, n);
    }
};
```