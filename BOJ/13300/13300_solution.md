```python
import sys
input = sys.stdin.readline
N, K = map(int, input().split())

student = [[0, 0] for _ in range(6)]

for _ in range(N):
    s, y = map(int, input().split())
    student[y-1][s] += 1

result = 0
for i in range(6):
    for j in range(2):
        result += ((student[i][j] + K - 1) // K)

print(result)
```



