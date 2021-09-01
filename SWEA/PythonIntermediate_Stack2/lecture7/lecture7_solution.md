```python
def getnextboard(board, a):
    new_board = []
    for i in range(1, len(board)):
        temp = []
        for j in range(len(board[i])):
            if j == a:
                continue
            temp.append(board[i][j])
        new_board.append(temp)
    return new_board

def get_sum_min(N, board, log, key, i):
    
    key_list = list(map(int, key))

    if i == N-1:
        for j in range(N):
            if key_list[j] == 0:
                # new_key_list = key_list[:]
                # new_key_list[j] = 1
                # new_key = ''.join(map(str, new_key_list))
                # log[new_key] = board[i][j]
                break      
        return board[i][j]
    else:
        tempmin = 1000

        for j in range(N):
            if key_list[j] == 0:
                new_key_list = key_list[:]
                new_key_list[j] = 1
                new_key = ''.join(map(str, new_key_list))
                if new_key in log:
                    tempsum = log[new_key] + board[i][j]
                else:
                    log[new_key] = get_sum_min(N, board, log, new_key, i+1)
                    tempsum = log[new_key] + board[i][j]
                if tempmin > tempsum:
                    tempmin = tempsum

        return tempmin


T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    board = [list(map(int, input().split())) for _ in range(N)]
    log_dict = {}
    key = '0'*N

    result = get_sum_min(N, board, log_dict, key, 0)
    answer.append(result)


for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



