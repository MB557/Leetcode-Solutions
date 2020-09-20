## 9. [Palindrome Number](https://leetcode.com/problems/palindrome-number/) :link:

Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

## Solution :heavy_check_mark:

```python3
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if (x<0):
            return False
        else:
            t1 = str(x)
            t2 = str(x)[::-1]
            if(t1 == t2):
                return True
            else:
                return False
```