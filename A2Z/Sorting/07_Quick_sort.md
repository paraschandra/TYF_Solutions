### 07. Quick Sort

**Problem Statement:** <br/>
Given an array of n integers, sort the array using the Quicksort method.

**Example:** <br/>
**Input**: N = 6, array[] = {13,46,24,52,20,9}

**Output**: 9,13,20,24,46,52

**Explanation**: After sorting the array is: 9, 13, 20, 24, 46, 52

**Code:** 
```cpp
class Solution {
  public:
    int partition(vector<int> &arr, int low, int high) {
        int pivot = arr[low];
        int i = low;
        int j = high;

        while (i < j) {
            while (arr[i] <= pivot && i <= high - 1) {
                i++;
            }

            while (arr[j] > pivot && j >= low + 1) {
                j--;
            }
            if (i < j) swap(arr[i], arr[j]);
        }
        swap(arr[low], arr[j]);
        return j;
    }

    void qs(vector<int> &arr, int low, int high) {
        if (low < high) {
            int pIndex = partition(arr, low, high);
            qs(arr, low, pIndex - 1);
            qs(arr, pIndex + 1, high);
        }
    }

    vector<int> quickSort(vector<int> arr) {
        qs(arr, 0, arr.size() - 1);
        return arr;
    }
};
```