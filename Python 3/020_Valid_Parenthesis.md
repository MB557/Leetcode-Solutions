## 20. [Valid Parenthesis](https://leetcode.com/problems/valid-parenthesis/) :link:

Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

    Open brackets must be closed by the same type of brackets.
    Open brackets must be closed in the correct order.

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