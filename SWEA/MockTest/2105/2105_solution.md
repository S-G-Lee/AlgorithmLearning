```python
def is_possible(N, i, j):
    if (0<= i < N) and (0 <= j < N):
        return True
    return False


def dfs(N, board, visited, start_i, start_j, i, j, direction, distance, desert):

    global result

    for idx in direction:
        di, dj = delta[idx][0], delta[idx][1]
        if is_possible(N, i+di, j+dj):
            if (i+di, j+dj) == (start_i, start_j):
                if result < distance:
                    result = distance
            elif not visited[i+di][j+dj] and board[i+di][j+dj] not in desert:
                new_desert = desert[:]
                new_desert.append(board[i+di][j+dj])
                visited[i+di][j+dj] = 1
                if idx < 3:
                    new_direction = [idx, idx+1]
                else:
                    new_direction = [idx]
                
                dfs(N, board, visited, start_i, start_j, i+di, j+dj, new_direction, distance+1, new_desert)
                visited[i+di][j+dj] = 0

    return




T = int(input())

result = -1
answer = []
delta = [(1, 1), (1, -1), (-1, -1), (-1, 1)]

for tc in range(1, T + 1):

    N = int(input())

    board = [list(map(int, input().split())) for _ in range(N)]

    corner = [(0, 0), (0, N-1), (N-1, 0), (N-1, N-1)]

    result = -1
    for start_i in range(N):
        for start_j in range(N):
            if (start_i, start_j) not in corner:
                visited = [[0 for _ in range(N)] for _ in range(N)]
                visited[start_i][start_j] = 1
                directed = [0, 1]
                desert = [board[start_i][start_j]]
                dfs(N, board, visited, start_i, start_j, start_i, start_j, directed, 1, desert)
                visited[start_i][start_j] = 0
                if result < 4:
                    result = -1
    
    # print(f'#{tc} {result}')
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



