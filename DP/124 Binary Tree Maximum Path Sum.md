刷题日期： 2026-03-11

难度：Hard

标签：动态规划(树形dp)

题目截图：![](assets/124%20Binary%20Tree%20Maximum%20Path%20Sum/file-20260311103943908.png)
代码:
```python
class Solution:

	def maxPathSum(self, root: TreeNode) -> int:
	
		ans = -inf
		
		def dfs(node):
		
			if node is None:
			
			return 0
			
			l_val = dfs(node.left)
			
			r_val = dfs(node.right)
			
			nonlocal ans
			
			ans = max(ans, l_val+r_val+node.val)
			
			return max(max(l_val,r_val)+node.val,0)
		
		dfs(root)
		
		return ans
```