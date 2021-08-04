```python
T = int(input())

for tc in range(1, T + 1):

    N = int(input())

    board = [[0 for _ in range(N)] for _ in range(N)]

    num = 1
    i, j = 0, 0
    go_i, go_j = 0, 1    
    while num <= N ** 2:
        
        board[i][j] = num
        if (not (0 <= i + go_i < N)) or (not (0 <= j + go_j < N)) or board[i + go_i][j + go_j] != 0:           
            go_i, go_j = go_j, -go_i

        i += go_i
        j += go_j
        num += 1
    
    print(f'#{tc} ')
    for i in board:
        result = ' '.join(list(map(str, i)))
        print(result)
```



