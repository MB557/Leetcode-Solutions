
## 3. [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/) :link:

Given a string s, find the length of the longest substring without repeating characters.

## Solution :heavy_check_mark:

```python3
        l,r,m,d=0,0,0,set()
        while r < len(s):
            if not s[r] in d:
                d.add(s[r])
                m = max(len(d),m)
                r += 1
            else:
                d.remove(s[l])
                l += 1
        return m
```
