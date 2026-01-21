刷题日期： 2026-01-20

难度：Medium

标签：动态规划

题目截图：
![](assets/322%20coin%20change/file-20260116222215263.png)
代码：
```python
class Solution:

	def coinChange(self, coins: List[int], amount: int) -> int:
		@cache
		def dfs(i,c):

			if i < 0:
				return 0 if c==0 else inf
			if c< coins[i]:
				return dfs(i-1,c)
			return min(dfs(i-1,c),dfs(i,c-coins[i])+1)

		ans = dfs(len(coins)-1,amount)
		
		return ans if ans<inf else -1
```

解题心得：