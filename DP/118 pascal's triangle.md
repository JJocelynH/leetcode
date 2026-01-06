刷题日期： 2026-01-05

难度：Easy

标签：动态规划

题目截图:
![](assets/118%20pascal's%20triangle/file-20260106114050612.png)
代码：

```python
def generate(self, numRows: int) -> List[List[int]]:
	c = [[1]\*(i+1) for i in range(numRows)]
	for i in range(2,numRows):
	for j in range(1,i):
	c[i][j] = c[i-1][j-1] + c[i-1][j]
	return c
```

解题心得:

- 将三角左对齐，每一个格都是它的左上方数字加正上方数字
- 主要是要注意双层循环的范围
