```python
T = int(input())

for tc in range(1, T + 1):

    N, K = list(map(int, input().split()))
    board = [ list(map(int, input().split())) for _ in range(N)]

    total = 0
    
    for i in range(N):
        for j in range(N):
            
            check = 0

            if board[i][j] == 1:

                check = 1
                if i - 1 < 0 or (i - 1 >= 0 and board[i - 1][j] == 0):
                    for k in range(K):
                        if i + k >= N or board[i + k][j] == 0:
                            check = 0
                            break
                    if check:
                        if i + K < N and board[i + K][j]:
                            check = 0
                    if check:
                        total += 1
                
                check = 1
                if i + 1 >= N or (i + 1 < N and board[i + 1][j] == 0):
                    for k in range(K):
                        if i - k < 0 or board[i - k][j] == 0:
                            check = 0
                            break
                    if check:
                        if i - K >= 0 and board[i - K][j]:
                            check = 0
                    if check:
                        total += 1

                check = 1
                if j - 1 < 0 or (j - 1 >= 0 and board[i][j - 1] == 0):
                    for k in range(K):
                        if j + k >= N or board[i][j + k] == 0:
                            check = 0
                            break
                    if check:
                        if j + K < N and board[i][j + K]:
                            check = 0
                    if check:
                        total += 1

                check = 1
                if j + 1 >= N or (j + 1 < N and board[i][j + 1] == 0):
                    for k in range(K):
                        if j - k < 0 or board[i][j - k] == 0:
                            check = 0
                            break
                    if check:
                        if j - K >= 0 and board[i][j - K]:
                            check = 0
                    if check:
                        total += 1
            
    total = total // 2

    print(f'#{tc} {total}')    
```



