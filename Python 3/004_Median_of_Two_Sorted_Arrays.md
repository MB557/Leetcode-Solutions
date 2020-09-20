## 4. [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) :link:

Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

## Solution :heavy_check_mark:


```python3
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
	
        nums1.extend(nums2)  #Extend nums1, thus storing all contents in a single list.
        nums1.sort()         #Sort the list
		
        if(len(nums1) % 2 == 0):
			#If length of list is even, return the average of the middle and the next element.
            return (((nums1[int(len(nums1)/2 - 1)]) + (nums1[int(len(nums1)/2)]))/2) 
        else:
			#Else, return the middle element
            return ((nums1[int(len(nums1)/2)]))
```