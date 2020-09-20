## 7. [Reverse Integer](https://leetcode.com/problems/reverse-integer/) :link:

Given a 32-bit signed integer, reverse digits of an integer.

## Solution :heavy_check_mark:


```python3
class Solution:
    def reverse(self, x: int) -> int:
        
        # If the integer is >= 0, then we first convert it to type ```string``` and reverse it.
        # However, if the integer is negative, the same process is repeated as above excluding the minus sign.
        # Thus, for negative integers, only the string from [1:] is considered (reversal is not performed on the oth index, i.e. the minus sign).
        
        result = int(str(x)[::-1]) if x >= 0 else -int(str(x)[1:][::-1])
        return result if -2**31 <= result <= 2**31 - 1 else 0
```

