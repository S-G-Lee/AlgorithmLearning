```python
def checkborder(H, W, i, j):
    if (0 <= i < H) and (0 <= j < W):
        return True
    return False

def getdirection(shape):
    if shape == '^':
        return -1, 0
    elif shape == 'v':
        return 1, 0
    elif shape == '>':
        return 0, 1
    elif shape == '<':
        return 0, -1


def play(board, H, W, i, j, c):

    if c == "U":
        board[i][j] = '^'
        if checkborder(H, W, i-1, j):
            if board[i-1][j] == '.':
                board[i][j] = '.'
                board[i-1][j] = '^'
                return i-1, j
    elif c == "D":
        board[i][j] = 'v'
        if checkborder(H, W, i+1, j):
            if board[i+1][j] == '.':
                board[i][j] = '.'
                board[i+1][j] = 'v'
                return i+1, j
    elif c == "R":
        board[i][j] = '>'
        if checkborder(H, W, i, j+1):
            if board[i][j+1] == '.':
                board[i][j] = '.'
                board[i][j+1] = '>'
                return i, j+1
    elif c == "L":
        board[i][j] = '<'
        if checkborder(H, W, i, j-1):
            if board[i][j-1] == '.':
                board[i][j] = '.'
                board[i][j-1] = '<'
                return i, j-1
    elif c == "S":
        idir, jdir = getdirection(board[i][j])
        bullet_i = i + idir
        bullet_j = j + jdir
        while checkborder(H, W, bullet_i, bullet_j):
            if board[bullet_i][bullet_j] == '*':
                board[bullet_i][bullet_j] = '.'
                break
            elif board[bullet_i][bullet_j] == '#':
                break
            bullet_i = bullet_i + idir
            bullet_j = bullet_j + jdir
    return i, j

T = int(input())

answer = []
for tc in range(1, T + 1):

    H, W = map(int, input().split())

    board = []
    starti, startj = 0, 0
    for _ in range(H):
        board.append(list(input()))

    for i in range(H):
        check = 0
        for j in range(W):
            if board[i][j] in '^v><':
                starti, startj = i, j
                check = 1
                break                
    
    N = int(input())

    commands = list(input())

    i, j = starti, startj
    for command in commands:
        i, j = play(board, H, W, i, j, command)

    result = ''
    for line in board:
        result += ''.join(line) + '\n'
    result = result.rstrip('\n')

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



