### 04. Merge Sort

**Problem Statement:** <br/>
Given an array of N integers, write a program to implement the Merge Sorting algorithm.

**Example:** <br/>
**Input**: N = 6, array[] = {13,46,24,52,20,9}

**Output**: 9,13,20,24,46,52

**Explanation**: After sorting the array is: 9, 13, 20, 24, 46, 52

**Code:** 
```cpp
class Solution {
  public:
    void merge(vector<int> &arr, int low, int mid, int high) {
        vector<int> temp;
        int left = low;
        int right = mid + 1;

        while (left <= mid && right <= high) {
            if (arr[left] <= arr[right]) {
                temp.push_back(arr[left]);
                left++;
            }
            else {
                temp.push_back(arr[right]);
                right++;
            }
        }

        while (left <= mid) {
            temp.push_back(arr[left]);
            left++;
        }

        while (right <= high) {
            temp.push_back(arr[right]);
            right++;
        }

        for (int i = low; i <= high; i++) {
            arr[i] = temp[i - low];
        }
    }

    void mergeSort(vector<int> &arr, int low, int high) {
        if (low >= high) return;
        int mid = (low + high) / 2 ;
        mergeSort(arr, low, mid);
        mergeSort(arr, mid + 1, high);
        merge(arr, low, mid, high);
    }
};
```