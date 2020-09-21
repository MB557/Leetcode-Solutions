## 20. [Valid Parenthesis](https://leetcode.com/problems/valid-parenthesis/) :link:

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

    Open brackets must be closed by the same type of brackets.
    Open brackets must be closed in the correct order.
    
## Visualization

![valid_p](https://user-images.githubusercontent.com/55105941/93742866-7f134d80-fc0c-11ea-8ca3-1d37ebbe3a4c.gif)

## Solution 1 - Easy stack implementation :heavy_check_mark:	

```python3
class Solution:
    def isValid(self, s: str) -> bool:
        
        # Stack for checking matching values.
        stack = [] 
        
        # A map for storing bracket pairs.
        brackets = { "(": ")","[": "]","{": "}" }

        for i in s:
            if i in brackets:
                stack.append(brackets[i])

            # Condition check:
            # i) Is the stack empty
            # ii) Is the popped value a matching value?
            
            elif len(stack) == 0 or stack.pop() != i:
                return False

        return len(stack) == 0
```
