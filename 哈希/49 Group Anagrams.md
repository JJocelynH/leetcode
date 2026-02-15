刷题日期： 2026-02-14

难度：Medium

标签：哈希

题目截图：
![](assets/49%20Group%20Anagrams/file-20260214222550043.png)

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
- 记得几个哈希的常用方法