## 22. [Generate Parentheses](https://leetcode.com/problems/generate-parentheses/) :link:

 Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

For example, given n = 3, a solution set is:

```[
  "((()))",
  "(()())",
  "(())()",
  "()(())",
  "()()()"
]
```

## Solution :heavy_check_mark:	

```python3
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        
        # List to store all sequences
        res = []
        
        # Using DFS to explore all possibilities.
        
        def dfs(s, left, right):
            if not right: 
                res.append(s)
            if left: 
                dfs(s+'(', left-1, right)
            if right > left: 
                dfs(s+')', left, right-1)

        
        dfs("", n, n)
        return res
 ```