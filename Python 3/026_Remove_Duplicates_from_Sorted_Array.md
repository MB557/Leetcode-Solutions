## 26. [Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/) :link:

Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

## Intuition :thought_balloon:

The idea here is to move from left to right in array and swapping elements that are duplicates out with elements we find that are not duplicates. If nums[i] and end[i+1] are not equal then we just swap the new element with the first found duplicate (and if there are no duplicates we essentially swap the element with itself for no impact). By the time we reach end of array all the duplicates have been swapped to the back end of array.


## Solution :heavy_check_mark:	

```python3
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        itr = 0
        for i in range(1, len(nums)):            
            if nums[i] != nums[itr]:
                nums[itr+1], itr = nums[i], itr + 1
        if nums:
            return itr + 1
        else:
            return 0
 ```

