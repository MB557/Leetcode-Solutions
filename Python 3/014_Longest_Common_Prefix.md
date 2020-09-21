## 14. [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/) :link:

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

## Solution 1 :heavy_check_mark:

```python3
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if strs == []:
            return ""
        
        a = strs[0]
        
        for i in strs:
            
            # Compare the letters of the string at 0th index.
            # If the other strings do not start with those letters, then
            # Remove the last letter from the 0th string, thus a = a[:-1].
            # Repeat the same steps as above until the condition becomes True.
            
            while i.startswith(a) == False:
                a = a[:-1]
        return a
```

## Solution 2 (One Liner) :heavy_check_mark:

```python3
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        return os.path.commonprefix(strs)
```