```python
N = int(input())
heights = list(map(int, input().split()))

can_see = [[0 for _ in range(N)] for _ in range(N)]

for i in range(N-1):
    for j in range(i+1, N):
        for k in range(i+1, j):
            slope = (heights[j] - heights[i]) / (j-i)
            if heights[i] + (slope * (k-i)) <= heights[k]:
                break
        else:
            can_see[i][j] = 1
            can_see[j][i] = 1

result = 0
for i in range(N):
    tempsum = sum(can_see[i])
    if result < tempsum:
        result = tempsum

print(result)
```



