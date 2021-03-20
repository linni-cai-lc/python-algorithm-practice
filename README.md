# Python-Practice

# Week 36 [5/3-5/9]

# [1173](https://leetcode.com/problems/immediate-food-delivery-i/)
```sql
SELECT ROUND(IMM.CNT * 100 / TOT.CNT,2) AS immediate_percentage
FROM (
    SELECT COUNT(*) AS CNT
    FROM Delivery
    WHERE order_date = customer_pref_delivery_date
) AS IMM, (
    SELECT COUNT(*) AS CNT
    FROM Delivery
) AS TOT;
```

# [1217](https://leetcode.com/problems/minimum-cost-to-move-chips-to-the-same-position/)
```python
def main(position):
    even, odd = 0, 0
    for i in position:
        if i % 2 == 0:
            even += 1
        else:
            odd += 1
    return min(even, odd)
```
#### Assumption: N = the number of elements in the given list
#### Complexity: runtime = O(N), space = O(1)

# [867](https://leetcode.com/problems/transpose-matrix/)
```python
def main(matrix):
    m = len(matrix)
    n = len(matrix[0])
    new_m = [[0] * m for _ in range(n)]
    for i in range(m):
        for j in range(n):
            new_m[j][i] = matrix[i][j]
    return new_m
```
#### Assumption: M = the row number of the given matrix, N = the column number of the given matrix
#### Complexity: runtime = O(MN), space = O(1) excluding returning result

### Template
# []()
```sql
```

# []()
```python
```
#### Assumption: N = ??
#### Complexity: runtime = O(?), space = O(?)