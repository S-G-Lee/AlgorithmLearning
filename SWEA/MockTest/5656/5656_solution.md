```python
from copy import deepcopy

delta = [(1, 0), (-1, 0), (0, 1), (0, -1)]


def is_possible(W, H, i, j):
    if (0 <= i < H) and (0 <= j < W):
        return True
    return False


def shoot(W, H, board, first_i, first_j):
    queue = []
    queue.append((first_i, first_j))
    count = 0
    while queue:
        i, j = queue.pop()
        boom_range = board[i][j]
        if boom_range != 0:
            count += 1
            board[i][j] = 0
            for lv in range(1, boom_range):
                for di, dj in delta:
                    if is_possible(W, H, i + (di * lv), j + (dj * lv)):
                        queue.append((i + (di * lv), j + (dj * lv)))
    return count


def fall(W, H, board):
    for j in range(W):
        for i in range(H-1, -1, -1):
            if board[i][j] != 0:
                k = 0
                while i + k + 1 < H and board[i + k + 1][j] == 0:
                    k += 1
                if k > 0:
                    board[i + k][j] = board[i][j]
                    board[i][j] = 0


def game(N, W, H, board, k, brick_remain):
    global result
    if k == N:
        if result > brick_remain:
            result = brick_remain
        return

    none_check = 0
    for j in range(W):
        for i in range(H):
            if board[i][j] != 0:
                new_board = deepcopy(board)
                destroyed_brick = shoot(W, H, new_board, i, j)
                fall(W, H, new_board)
                game(N, W, H, new_board, k+1, brick_remain - destroyed_brick)
                break
        else:
            none_check += 1
    
    if none_check == W:
        if result > brick_remain:
            result = brick_remain
        return


T = int(input())

answer = []
for tc in range(1, T + 1):

    N, W, H = map(int, input().split())

    total_brick = 0
    board = []
    for _ in range(H):
        temp = list(map(int, input().split()))
        for j in range(W):
            if temp[j] != 0:
                total_brick += 1
        board.append(temp)

    result = total_brick
    game(N, W, H, board, 0, total_brick)
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



