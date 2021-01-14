# Python-Practice

# Week 22 [1/24-1/30]

# [1652](https://leetcode.com/problems/defuse-the-bomb/)
```python
def main(code, k):
   res = [0] * len(code)
   pos = 1 if k > 0 else -1
   for i in range(len(code)):
      sumi = 0
      for j in range(1, abs(k) + 1):
         sumi += code[(i + pos * j) % len(code)]
      res[i] = sumi
   return res
```
#### Assumption: C = the number of codes in the given list, K = the sum range 
#### Complexity: runtime = O(CK), space = O(C) for result list, same size of code list

# [1565](https://leetcode.com/problems/unique-orders-and-customers-per-month/submissions/)
```sql
SELECT CONCAT(YEAR(order_date), "-",
         RIGHT(CONCAT("0", MONTH(order_date)), 2)
       ) AS month,
       COUNT(DISTINCT order_id) AS order_count,
       COUNT(DISTINCT customer_id) AS customer_count
FROM Orders
WHERE invoice > 20
GROUP BY month
```

# [1056](https://leetcode.com/problems/confusing-number/)
```python
def main(N):
   book = {
      "0": "0",
      "1": "1",
      "6": "9",
      "8": "8",
      "9": "6"
   }
   res = ""
   pre = str(N)
   for i in pre:
      if i not in book:
         return False
      else:
         res += book[i]
   return res[::-1] != pre
```
#### Assumption: N = the length of the number string
#### Complexity: runtime = O(N), space = O(N) return the result string

### Template
# []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)