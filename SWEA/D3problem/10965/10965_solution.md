```python
def checkomok(N, board, i, j, i_dir, j_dir):

    line = 0
    while line < 5:

        if board[i][j] == 'o':
            line += 1
            i = i + i_dir
            j = j + j_dir
        else:
            break

        if not (0 <= i < N):
            break
        if not (0 <= j < N):
            break
     
    if line == 5:
         return True
    return False

        

T = int(input())

for tc in range(1, T + 1): 

    N = int(input())
    board = [list(input()) for _ in range(N)]
    directionlist = [(1,0), (1,1), (0,1), (-1,1), (-1,0), (-1,-1), (0,-1), (1,-1)]

    check = False
    for i in range(N):
        for j in range(N):
            for i_dir, j_dir in directionlist:
                check = checkomok(N, board, i, j, i_dir, j_dir)
                if check:
                    break
            if check:
                break
        if check:
            break
    
    result = 'NO'
    if check:
        result = 'YES'
    print(f'#{tc} {result}')
```



