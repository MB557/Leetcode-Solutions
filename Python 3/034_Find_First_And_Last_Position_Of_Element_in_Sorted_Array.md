## 34. [Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) :link:

Given an array of integers nums sorted in ascending order, find the starting and ending position of a given target value.

Your algorithm's runtime complexity must be in the order of ``` O(log n) ```.

If the target is not found in the array, return [-1, -1].
```
Example 1:

Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```
## Solution (using binary search) :heavy_check_mark:	

```python3
class Solution:
    def searchRange(self, nums: List[int], target: int) -> List[int]:

        l, r = 0, len(nums) - 1

        while(l <= r):
            
            #Computing mid index
            mid = (l + r) // 2
            
            #Regular Binary Search
            if(nums[mid] == target):
                left, right = mid, mid
                
                while(True):
                    if(left < l or nums[left] != target):
                        left += 1
                        break
                    left -= 1
                    
                while(True):
                    if(right > r or nums[right] != target):
                        right -= 1
                        break
                    right += 1
                    
                return [left, right]
            
            elif(nums[mid] < target):
                l = mid + 1
                
            else:
                r = mid - 1
                
        return [-1, -1]
```