## 21. [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/) :link:

Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the first two lists.

## Intuition :thought_balloon:

Have a while loop that cycles through both lists -- as long as both lists have at least one node. When I've exhausted at least one of the lists, I do a final check to append what's left of the longer list.

This solution is most performant when you have two lists that are very different in length.

## Solution :heavy_check_mark:	

```python3
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:

        root = curr = ListNode(0)
        
        while l1 and l2:
            if l1.val < l2.val:
                # point to the smaller value
                curr.next = l1
                # advance the linked lists
                curr = curr.next
                l1 = l1.next
            else: 
                # point to the smaller value
                curr.next = l2
                # advance the linked lists
                curr = curr.next
                l2 = l2.next

        # now that we've exhausted at least 
        # one of the lists, let's tag on anything that's remaining
        if not l1:
            curr.next = l2
        if not l2:
            curr.next = l1

        return root.next
```

