## 28. [Implement strStr()](https://leetcode.com/problems/implement-strstr/) :link:

Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.
```
Example 1:

Input: haystack = "hello", needle = "ll"
Output: 2

Example 2:

Input: haystack = "aaaaa", needle = "bba"
Output: -1
```
## Solution - 1 liner (using find):heavy_check_mark:	

```python3
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        return (haystack.find(needle))          
```


