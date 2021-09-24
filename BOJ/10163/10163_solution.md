```python
board = [[0 for _ in range(1001)] for _ in range(1001)]

N = int(input())
paper = [list(map(int, input().split())) for _ in range(N)] # paper[i] : x1, y1, w, h

for n in range(N):
    for i in range(paper[n][0], paper[n][0] + paper[n][2]):
        for j in range(paper[n][1], paper[n][1] + paper[n][3]):
            board[i][j] = n+1

for n in range(N):
    total = 0
    for i in range(1001):
        for j in range(1001):
            if board[i][j] == n+1:
                total += 1
    print(total)
```



