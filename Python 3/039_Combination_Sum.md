## 39. [Combination Sum](https://leetcode.com/problems/combination-sum/) :link:

Given a set of candidate numbers (candidates) (without duplicates) and a target number (target), find all unique combinations in candidates where the candidate numbers sums to target.

The same repeated number may be chosen from candidates unlimited number of times.

Note:

    All numbers (including target) will be positive integers.
    The solution set must not contain duplicate combinations.
```
Example 1:

Input: candidates = [2,3,6,7], target = 7,
A solution set is:
[
  [7],
  [2,2,3]
]
```
## Visualization

![Screenshot from 2020-09-22 12-43-12](https://user-images.githubusercontent.com/55105941/93853388-6a4cbd80-fcd1-11ea-9afc-b918be5128c6.png)

## Solution - Using DFS :heavy_check_mark:	

```python3
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:

        res=[]
        self.dfs(res,[],sorted(candidates),target)
        return res
        
    def dfs(self,res, path,candidates,target):
        if target < candidates[0]:
            return 

        for i in range(len(candidates))[::-1]:

            # Condition check: if true, return the only path possible.
            if candidates[i] == target:
                res.insert(0, [candidates[i]] + path)

            # if smaller, try it and keep searching for candidates that are smaller
            # candidates[:i+1] to avoid duplicates

            elif candidates[i] < target:
                self.dfs(res, [candidates[i]] + path, candidates[:i+1], target - candidates[i])
```
