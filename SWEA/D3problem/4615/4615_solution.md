```python
def change_color(board, color, i, j):

    N = len(board)
    dirlist = [(a, b) for a in [-1, 0, 1] for b in [-1, 0, 1] if not (a == b == 0)]

    for a, b in dirlist:
        check = 0
        step = 1
        while ((0 <= i + (step * a) < N) and (0 <= j + (step * b) < N)):
            if board[i + (step * a)][j + (step * b)] == color:
                check = 1
                break
            step += 1
        if check:
            check2 = 1
            step2 = step - 1
            while step2 > 0:
                if board[i + (step2 * a)][j + (step2 * b)] == 0:
                    check2 = 0
                    break
                step2 -= 1
            if check2:
                for x in range(1, step):
                    board[i + (x * a)][j + (x * b)] = color

T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())
    queue = []
    # black : 1, white : 2
    for i in range(M):
        queue.append(list(map(int, input().split())))

    board = [[0 for _ in range(N)] for _ in range(N)]
    board[(N//2)-1][(N//2)-1] = 2
    board[(N//2)][(N//2)-1] = 1
    board[(N//2)-1][(N//2)] = 1
    board[(N//2)][(N//2)] = 2

    for j, i, color in queue:
        i = i - 1
        j = j - 1
        board[i][j] = color
        change_color(board, color, i, j)

    b = 0
    w = 0
    for line in board:
        for pos in line:
            if pos == 1:
                b += 1
            elif pos == 2:
                w += 1
    result = f'{b} {w}'
    answer.append(result)
    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



