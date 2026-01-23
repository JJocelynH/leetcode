刷题日期： 2026-01-23

难度：Medium

标签：动态规划

题目截图：
![](assets/416%20Partition%20Equal%20Subset%20Sum/file-20260123161417734.png)
代码：
```python
class Solution:
	def canPartition(self, nums: List[int]) -> bool:
		@cache
		def dfs(i:int,j:int):
			if i < 0:
				return j == 0
			if j < nums[i]:
				return dfs(i-1,j)
			return dfs(i-1, j) or dfs(i-1,j-nums[i])
		s = sum(nums)
		return s%2==0 and dfs(len(nums)-1,s//2)

```

心得：
- DP 时间复杂度 = 状态数 × 每个状态的转移代价
- 这个是用最终的和等于零来判断是否符合条件，所以不选的时候是直接把现在的和带到下一层，选的话是把现在的和减去当前下标的值