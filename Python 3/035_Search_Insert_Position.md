## 35. [Search Insert Position](https://leetcode.com/problems/search-insert-position/) :link:

Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You may assume no duplicates in the array.
```
Example 1:

Input: [1,3,5,6], 5
Output: 2
```

## Visualizing the solution by using Binary Search :thought_balloon:

![searchInsertPosition](https://user-images.githubusercontent.com/55105941/93847764-76328280-fcc5-11ea-9c84-54f2f8354c6c.gif)

## Solution 1: Binary Search O(log N):heavy_check_mark:	

```python3
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        if target > nums[-1]:
            return len(nums)
        
        low, high = 0, len(nums) - 1
        
        while low <= high:
                mid = (high + low) // 2
                if nums[mid] == target:
                    return mid
                elif nums[mid] <= target:
                    low = mid + 1
                else:
                    high = mid - 1
        return low

```

## Solution 2: Using ```bisect()``` :heavy_check_mark:	

```python3
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
		return bisect.bisect_left(nums, target)
```

## Solution 3: Common approach O(n):heavy_check_mark:	

```python3
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
		if target not in nums:  
			nums.append(target)
		nums.sort()
		return nums.index(target)
```
