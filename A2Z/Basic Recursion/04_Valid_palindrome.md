### 04. Valid Palindrome

**Problem Statement:** <br/>
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

**Example:** <br/>
**Input**: s = "A man, a plan, a canal: Panama"

**Output**: true

**Explanation**: "amanaplanacanalpanama" is a palindrome.

**Code:** 
```cpp
class Solution {
public:
    bool valid(int i, string &s) {
        if(i >= s.length()/2)
            return true;
        
        if(s[i] != s[s.length()-i-1])
            return false;
        
        return valid(i+1, s);
    }

    bool isPalindrome(string s) {
        std::transform(s.begin(), s.end(), s.begin(), ::tolower);
        s.erase(std::remove_if(s.begin(), s.end(), [](char c) { 
            return !isalnum(c); 
        }), s.end());
        
        if (s.length() < 1) {
            return true;
        }
        return valid(0, s);
    }
};
```