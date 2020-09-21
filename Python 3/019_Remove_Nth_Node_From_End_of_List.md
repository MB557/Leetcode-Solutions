## 19. [Remove Nth Node from End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/) :link:

Given a linked list, remove the n-th node from the end of list and return its head.

## Visualization

![ll](https://user-images.githubusercontent.com/55105941/93741585-58541780-fc0a-11ea-96ca-635bda1e895c.gif)

## Solution 1 - Easy to understand :heavy_check_mark:	

```python3
class Solution:
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        start, lenOfList = head, 0
        
        # Computing length of Linked List.
        
        while(start):
            lenOfList += 1
            start = start.next
        
        # If n == lenOfList, it means removing (skipping) the first element.
        # Thus, I return head.next (all elements after the head node)
        
        if lenOfList == n:
            return head.next
        
        # Else, iterate till node (n-1) where n is the node to be removed.
        # Skip the nth node by pointing cur.next to cur.next.next.
        
        else:
            cur = head
            for i in range(lenOfList - n - 1):
                cur = cur.next
            cur.next = cur.next.next
            return head
```
