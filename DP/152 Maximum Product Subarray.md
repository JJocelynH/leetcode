刷题日期： 2026-01-23

难度：Medium

标签：动态规划

题目截图
![](assets/152%20Maximum%20Product%20Subarray/file-20260123154217450.png)
代码：
```python
class Solution:
	def maxProduct(self, nums: List[int]) -> int:
		n = len(nums)
		f_max = n*[0]
		f_min = n*[0]
		for i in range(1,n):
			x = nums[i]
			f_max[i] = max(f_max[i-1]*x, f_min[i-1]*x, x)
			f_min[i] = min(f_max[i-1]*x, f_min[i-1]*x, x)
		return max(f_max)
		
```

心得：
- 我们可以一直检查记录以下标i结尾的最大乘积和最小乘积（因为有复数，这样做就不用检查正负）