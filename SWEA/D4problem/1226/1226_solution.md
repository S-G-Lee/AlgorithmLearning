```python
def find_start(N, board):
    for i in range(N):
        for j in range(N):
            if board[i][j] == 2:
                return i, j


def promising(N, maze, i, j):
    if maze[i][j] != 1:
        return True
    return False


def bfs(N, maze, visited, start_i, start_j):

    delta = [[-1, 0], [1, 0], [0, -1], [0, 1]]
    q = []
    q.append([start_i, start_j])
    while q:
        i, j = q.pop(0)
        if not visited[i][j]:
            visited[i][j] = 1
            if maze[i][j] == 3:
                return 1
            for di, dj in delta:
                if promising(N, maze, i+di, j+dj) and not visited[i+di][j+dj]:
                    q.append([i+di, j+dj])
    return 0


# T = int(input())
T = 10

answer = []
for tc in range(1, T+1):
    testcase = int(input())
    N = 16
    maze = [list(map(int, input())) for _ in range(N)]

    visited = [[0 for _ in range(N)] for _ in range(N)]
    start_i, start_j = find_start(N, maze)

    result = bfs(N, maze, visited, start_i, start_j)
    answer.append(result)

for tc in range(1, T+1):
    print('#{} {}'.format(tc, answer[tc-1]))

```



