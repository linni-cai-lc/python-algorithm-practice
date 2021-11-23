# Python-Practice

# Week 82 [3/21-3/27]

# [1817](https://leetcode.com/problems/finding-the-users-active-minutes/)
```python
from collections import defaultdict as dd
def main(logs, k):
   book = dd(set)
   res = [0] * k
   for i, j in logs:
      book[i].add(j)
   for i in book:
      size = len(book[i])
      if size <= k:
         res[size - 1] += 1
   return res
```
#### Assumption: N = the number of logs
#### Complexity: runtime = O(N), space = O(N)

# [1740](https://leetcode.com/problems/find-distance-in-a-binary-tree/)
```python
def main(root, p, q):
   if p == q:
      return 0
   def dfs(cur):
      if not cur:
         return
      val = cur.val
      if val == p or val == q:
         return cur
      left = dfs(cur.left)
      right = dfs(cur.right)
      if left and right:
         return cur
      else:
         return left or right
   
   def distance(cur, target):
      if not cur:
         return sys.maxsize
      if cur.val == target:
         return 0
      return 1 + min(distance(cur.left, target), distance(cur.right, target))
   
   ancestor = dfs(root)
   return distance(ancestor, p) + distance(ancestor, q)
```
#### Assumption: N = the number of nodes in the tree
#### Complexity: runtime = O(N), space = O(N) with recursive callstack

# [1925](https://leetcode.com/problems/count-square-sum-triples/)
```python
def main(n):
   cnt = 0
   for i in range(1, n+1):
      for j in range(i, n+1):
         sumi = i**2 + j**2
         sq = int(math.sqrt(sumi))
         if 1 <= sumi <= n ** 2 and sq ** 2 == sumi:
            cnt += 1
            if i != j:
               cnt += 1
   return cnt
```
#### Assumption: N = the size of the given number
#### Complexity: runtime = O(N^2), space = O(1)

# [2078](https://leetcode.com/problems/two-furthest-houses-with-different-colors/)
```python
def main(colors):
   size = len(colors)
   right = size - 1
   maxi = 0
   while right > 0:
      if colors[right] != colors[0]:
         maxi = max(maxi, right)
         break
      right -= 1
   left = 0
   while left < size - 1:
      if colors[left] != colors[-1]:
         maxi = max(maxi, size - left - 1)
         break
      left += 1
   return maxi
```
#### Assumption: N = the number of elements in the colors
#### Complexity: runtime = O(N), space = O(1)

# [1472](https://leetcode.com/problems/design-browser-history/)
```python
class BrowserHistory:

    def __init__(self, homepage: str):
        self.lst = [homepage]
        self.idx = 0
        self.end = 0
        

    def visit(self, url: str) -> None:
        self.idx += 1
        if self.idx == len(self.lst):
            self.lst += [url]
        else:
            self.lst[self.idx] = url
        self.end = self.idx
        

    def back(self, steps: int) -> str:
        self.idx = max(0, self.idx - steps)
        return self.lst[self.idx]
        

    def forward(self, steps: int) -> str:
        self.idx = min(self.end, self.idx + steps)
        return self.lst[self.idx]
```
#### Assumption: N = the number of links
#### Complexity:
- space = O(N)
- visit: runtime = O(1)
- back: runtime = O(1)
- forward: runtime = O(1)

### Template
# []()
```sql
```

# []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)
