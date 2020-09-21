## 33. [Search In Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/) :link:

You are given an integer array nums sorted in ascending order, and an integer target.

Suppose that nums is rotated at some pivot unknown to you beforehand (i.e., [0,1,2,4,5,6,7] might become [4,5,6,7,0,1,2]).

If target is found in the array return its index, otherwise, return -1.

```
Example 1:

Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
```
## Solution - 1 liner (using index):heavy_check_mark:	

```python3
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        return nums.index(target) if target in nums else -1        
```