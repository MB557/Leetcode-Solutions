## 8. [String to Integer](https://leetcode.com/problems/string-to-integer-atoi/) :link:

Implement atoi which converts a string to an integer.

The function first discards as many whitespace characters as necessary until the first non-whitespace character is found. Then, starting from this character, takes an optional initial plus or minus sign followed by as many numerical digits as possible, and interprets them as a numerical value.

The string can contain additional characters after those that form the integral number, which are ignored and have no effect on the behavior of this function.

If the first sequence of non-whitespace characters in str is not a valid integral number, or if no such sequence exists because either str is empty or it contains only whitespace characters, no conversion is performed.

If no valid conversion could be performed, a zero value is returned.

Note:

    Only the space character ' ' is considered as whitespace character.
    Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. If the numerical value is out of the range of representable values, INT_MAX (231 − 1) or INT_MIN (−231) is returned.


## Solution :heavy_check_mark:


```python3
class Solution:
    def myAtoi(self, str: str) -> int:
        if len(str) == 0: 
            return 0
        ans, sign = 0, 1
        number_started = False
        minNum, maxNum = (-1) * (2 ** 31), (2 ** 31 - 1)
            
        for ch in str:       
            if number_started == False:                    
                if ch == ' ':
                    continue
                if ch =='-':
                    number_started = True
                    sign = -1
                    continue
                if ch == '+':
                    number_started = True
                    continue
                if ch.isdigit():
                    number_started = True
                        
            if ch.isdigit():
                ans = ans*10 + (ord(ch) - ord('0'))
            else:
                break

        ans = sign * ans 
            
        if ans == 0:
            return 0   
            
        elif ans < minNum:
            return minNum
            
        elif ans > maxNum:
            return maxNum
            
        else:
            return ans
```