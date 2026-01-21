刷题日期： 2026-01-21

难度：Medium

标签：动态规划

题目截图：
![](assets/300%20longest%20increasing%20subsequence/file-20260121173940828.png)
代码：
```python
class Solution:

	def lengthOfLIS(self, nums: List[int]) -> int:
		@cache
		def dfs(i:int):
			res = 0
			for j in range(i):
				if nums[j] < nums[i]:
					res = max(res,dfs(j))
			return res + 1
		return max(dfs(i) for i in range(len(nums)))
			
	

```
心得：
- 这个是枚举选哪个，时间复杂度是O(n^2)