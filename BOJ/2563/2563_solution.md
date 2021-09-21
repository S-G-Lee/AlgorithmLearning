```python
N = int(input())
board = [[0 for _ in range(100)] for _ in range(100)]

result = 0
for _ in range(N):
    x, y = map(int, input().split())
    for i in range(y, y+10):
        for j in range(x, x+10):
            if board[i][j] == 0:
                board[i][j] = 1
                result += 1

print(result)
```



