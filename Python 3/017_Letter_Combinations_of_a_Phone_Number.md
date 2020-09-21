## 17. [Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/) :link:

Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent.

A mapping of digit to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

## Intuition

The question simply asks for a cartesian product of the letters represented by the digits. Thus, I have made use of the itertools.product() module. itertools.product() returns a list of tuples with each tuple representing a possible string. The list comprehension in the return statement simply joins the elements in each tuple to make it a string, iterating over all tuples returned by itertools.product(). The \*res allows us to pass a list of arguments as a single list as itertools.product() requires the iterables to be separate arguments.


## Solution 1 :heavy_check_mark:

```python3
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:

        from itertools import product as pd
        res = []
        digitMap = {2:'abc', 3:'def', 4:'ghi', 5:'jkl', 6:'mno', 7:'pqrs', 8:'tuv', 9:'wxyz'}
        
        if not digits:
            return res
        
        for i in digits:
            res.append(digitMap[int(i)])
        
        return ["".join(x for x in y) for y in pd(*res)]
```