```python
def move(i, j, dir_num):
    if dir_num == 1:
        return i-1, j
    elif dir_num == 2:
        return i+1, j
    elif dir_num == 3:
        return i, j-1
    elif dir_num == 4:
        return i, j+1


def reverse_dir(dir_num):
    if dir_num == 1:
        return 2
    elif dir_num == 2:
        return 1
    elif dir_num == 3:
        return 4
    elif dir_num == 4:
        return 3


def is_border(N, i, j):
    if (0 < i < N-1) and (0 < j < N-1):
        return False
    return True


T = int(input())

answer = []
for tc in range(1, T + 1):

    # 셀의 개수 N, 격리 시간 M, 미생물 군집의 개수 K
    N, M, K = map(int, input().split())
    
    board = [[[] for _ in range(N)] for _ in range(N)]

    # 세로위치, 가로위치, 개수, 이동방향
    microorganism = [[0, 0, 0, 0] for _ in range(K)]
    # 이동방향 : 1상 2하 3좌 4우
    for idx in range(K):
        i, j, n, d = map(int, input().split())
        microorganism[idx][0] = i
        microorganism[idx][1] = j
        microorganism[idx][2] = n
        microorganism[idx][3] = d
        board[i][j].append(idx)

    for _ in range(M):
        for idx in range(K-1, -1, -1):
            i, j, n, d = microorganism[idx]
            if n > 0:
                board[i][j].remove(idx)
                i, j = move(i, j, d)
                microorganism[idx][0] = i
                microorganism[idx][1] = j
                if is_border(N, i, j):
                    n //= 2
                    microorganism[idx][2] = n
                    microorganism[idx][3] = reverse_dir(d)  
                board[i][j].append(idx)              
        
        for i in range(N):
            for j in range(N):
                if len(board[i][j]) > 1:
                    total = 0
                    max_num = 0
                    max_idx = -1
                    for idx in board[i][j]:
                        total += microorganism[idx][2]
                        if max_num < microorganism[idx][2]:
                            max_num = microorganism[idx][2]
                            max_idx = idx
                    
                    microorganism[max_idx][2] = total
                    for idx in board[i][j]:
                        if idx == max_idx:
                            microorganism[idx][2] = total
                        else:
                            microorganism[idx][2] = 0
                    board[i][j] = [max_idx]
     
    result = 0
    for i in range(len(microorganism)):
        result += microorganism[i][2]
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



