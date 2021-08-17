```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    word = input()
    N = len(word)

    board = [['.' for _ in range(4*N + 1)] for _ in range(5)]

    for i in range(N):
        board[0][4*i + 2] = '#'
        board[1][4*i + 1] = '#'
        board[1][4*i + 3] = '#'
        board[2][4*i] = '#'
        board[2][4*i + 2] = word[i]
        board[2][4*i + 4] = '#'
        board[3][4*i + 1] = '#'
        board[3][4*i + 3] = '#'
        board[4][4*i + 2] = '#'        

    result = [''.join(x) for x in board]
    answer.append(result)

for tc in range(1, T+1):
    for i in range(5):
        print(f'{answer[tc-1][i]}')
```



