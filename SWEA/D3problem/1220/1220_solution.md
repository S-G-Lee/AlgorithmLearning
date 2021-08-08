```python
T = 10

answer = []
for tc in range(1, T + 1):

    N = int(input())

    board = []
    for i in range(N):
        board.append(list(map(int, input().split())))

    count = 0
    result = 0
    for j in range(N):
        count1 = 0
        temp = 0
        for i in range(N):
            if temp == 0 and board[i][j] == 1:
                temp = 1
            elif temp != 0 and board[i][j] == 2:
                count1 += 1
                temp = 0
        count += count1

    result = count

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



