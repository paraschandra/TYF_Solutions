### 03. Check Palindrome

**Problem Statement:** <br/>
Given an integer x, return true if x is a palindrome, and false otherwise.

**Example:** <br/>
**Input**: x = 121

**Output**: true

**Explanation**: 121 reads as 121 from left to right and from right to left.

**Code:** 
```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if(x < 0) return false;
        long long tmp = x, rev = 0;

        while(x){
            int ld = x % 10;
            rev = rev * 10 + ld;
            x /= 10;
        }

        return (tmp == rev);
    }
};
```