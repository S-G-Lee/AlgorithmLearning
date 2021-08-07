```python
T = 10

answer = []
for tc in range(1, T + 1):

    nothing = input()
    board = []
    for _ in range(100):
        board.append(list(map(int, input().split())))

    row = [0] * 100
    col = [0] * 100
    cross = [0, 0]
    for i in range(100):
        for j in range(100):
            row[j] += board[i][j]
            col[i] += board[i][j]
            if i == j:
                cross[0] += board[i][j]
            elif i == 100 - 1 - j:
                cross[1] += board[i][j]
    
    result = max(max(row), max(col), max(cross))
    
    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



