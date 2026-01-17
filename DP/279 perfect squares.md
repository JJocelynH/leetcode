刷题日期： 2026-01-16

难度：Medium

标签：动态规划

题目截图：
![](assets/279%20perfect%20squares/file-20260116215734609.png)
代码
```python
@cache
def dfs(i,j):
	if i = 0:
		return inf if j else 0
	if j < i*i:
		return dfs(i-1,j)
	return min(dfs(i-1,j),dfs(i,j-i*i)+1)
	
class Solution:
	def numSquares(self, n:int):
		dfs(isqrt(n),n)
		
```

解题心得：
- i可以复用，所以dfs选的话也是代入i
- @cache要写在类外面，不然每次迭代都会重新创建cache就会需要重新创建，这样cache就不能起作用
- isqrt是向下取整平方根