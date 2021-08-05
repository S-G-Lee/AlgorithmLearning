```python
T = int(input())

for tc in range(1, T + 1):

    N = 9 # 9 : sdoku size
    sdoku_board = [ list(map(int, input().split())) for _ in range(N)] # N * N array (9 * 9)

    check = 1
    # row check
    for i in range(N):

        checklist = [0] * N

        for j in range(N):

            if checklist[sdoku_board[i][j] - 1]:
                check = 0
                break
            else:
                checklist[sdoku_board[i][j] - 1] = 1

    # column check
    for i in range(N):

        checklist = [0] * (N + 1)

        for j in range(N):

            if checklist[sdoku_board[j][i] - 1]:
                check = 0
                break
            else:
                checklist[sdoku_board[j][i] - 1] = 1

    # square check
    for i in range(0, N, 3):
        for j in range(0, N, 3):

            checklist = [0] * N

            for k in range(3):
                for l in range(3):

                    if checklist[sdoku_board[i+k][j+l] - 1]:
                        check = 0
                        break
                    else:
                        checklist[sdoku_board[i+k][j+l] - 1] = 1
    
    result = 0
    if check:
        result = 1
    print(f'#{tc} {result}')
```



