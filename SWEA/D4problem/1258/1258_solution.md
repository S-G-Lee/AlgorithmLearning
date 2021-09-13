```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    board = []
    for _ in range(N):
        board.append(list(map(int, input().split())))
    
    boardcheck = [[0 for _ in range(N)] for _ in range(N)]

    boxes = []
    for i in range(N):
        for j in range(N):
            if boardcheck[i][j] == 0:
                if board[i][j] != 0:
                    k = 0
                    while j+k < N and board[i][j+k] != 0:
                        k += 1
                    l = 0
                    while i+l < N and board[i+l][j+k-1] != 0:
                        l += 1
                    boxes.append([l, k])
                    for y in range(i, i+l):
                        for x in range(j, j+k):
                            boardcheck[y][x] = 1

    boxes.sort(key=lambda x:(x[0]*x[1], x[0]))

    result = []
    result.append(len(boxes))
    for box in boxes:
        result.append(box[0])
        result.append(box[1])
    
    result = ' '.join(map(str, result))

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



