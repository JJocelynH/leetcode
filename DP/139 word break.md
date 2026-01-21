刷题日期： 2026-01-20

难度：Medium

标签：动态规划

题目截图：
![](assets/139%20word%20break/file-20260116222315054.png)
代码：
```python
class Solution:
	def wordBreak(self, s: str, wordDict: List[str]) -> bool:
		max_len = max(map(len,wordDict))
		words = set(wordDict)
		
		@cache
		def dfs(i:int):
			if i == 0:
				return True
			
			for j in range(i-1,max((i-max_len-1),-1),-1):
				if s[j:i] in words and dfs(j):
					return True
			return False
			
		return dfs(len(s))

```

解题心得：
- @cache只能加在def和class之前
- max(map(len,wordDict))等价于max_len = max(len(word) for word in wordDict)
- words = set(wordDict)为了减少s[j:i] in words的搜索时间
- for j in range(i-1,max((i-max_len-1),-1),-1) 为了剪枝，每次搜索只搜索不大于max_len的长度