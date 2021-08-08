```python
def is_pal(word):
    
    check = 1
    while word:
        if word[0] != word[-1]:
            check = 0
            break
        word = word[1:-1]
    if check:
        return True
    return False


# T = int(input())
T = 10

answer = []
for tc in range(1, T + 1):

    nothing = int(input())
    
    board = []
    for _ in range(100):
        board.append(input())

    result = 0
    for i in range(100):
        for j in range(100):
            length = 1
            k = 1
            while j+k < 100:
                if board[i][j+k] == board[i][j]:
                    if is_pal(board[i][j:j+k+1]):
                        if length < k+1:
                            length = k+1
                k += 1

            if result < length:
                result = length

            k = 1
            length = 1
            while i+k < 100:
                if board[i+k][j] == board[i][j]:
                    word = ''
                    for x in range(i, i+k+1):
                        word += board[x][j]
                    if is_pal(word):
                        if length < k+1:
                            length = k+1
                k += 1

            if result < length:
                result = length
                

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



