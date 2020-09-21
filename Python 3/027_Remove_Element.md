## 27. [Remove Element](https://leetcode.com/problems/remove-element/) :link:

Given an array nums and a value val, remove all instances of that value in-place and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

Example 1:

```
Given nums = [3,2,2,3], val = 3,

Your function should return length = 2, with the first two elements of nums being 2.

It doesn't matter what you leave beyond the returned length.
```

## Solution :heavy_check_mark:	

```python3
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:

    	# A for loop is executed for N number of times where N = frequency of the given value.
    	# To count the frequency of an element in an array, the count() function is used.
    	# In each iteration, the value is removed from the array (one-by-one).
    	
        for i in range(nums.count(val)):
            nums.remove(val)
        return len(nums)
```
