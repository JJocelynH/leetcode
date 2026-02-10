刷题日期： 2026-02-09

难度：Medium

标签：哈希

题目截图：![](file-20260209231010500.png)
代码：
```python
class Solution:
	def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
		d = defaultdict(list)
		for s in strs:
			sorted_s = "".join(sorted(s))
			d[sorted_s].append(s)
		return list(d.values())
```
心得：
- 主要是要搞清楚用法，list()就是直接做成列表，sorted(s)是按照字母顺序排