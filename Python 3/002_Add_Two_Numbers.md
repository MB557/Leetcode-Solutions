## 2. [Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)  :link:

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

## Solution :heavy_check_mark:

```python3
class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        one = ''
        two = ''
        
        #check if l1 is valid and push values into string
        while l1:
            one += str(l1.val)
            l1 = l1.next
        
        #check if l2 is valid and push values into string
        while l2:
            two += str(l2.val)
            l2=l2.next
            
        result = str(int(one[::-1]) + int(two[::-1])) #adding the two strings
        result = result[::-1] #reversing the string
        
        cur = dummy = ListNode(0)
        for x in result:
            cur.next = ListNode(x)
            cur = cur.next
        
        return dummy.next
```

