```python
def is_triangle(graph, i, j, k):
    
    if graph[i][j] == 1:
        if graph[j][k] == 1:
            if graph[k][i] == 1:
                return True
    return False


T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N, M = map(int, input().split())
    graph = [[0 for _ in range(N)] for _ in range(N)] # graph[i][j]: check node from i to j
    for _ in range(M):
        x, y = map(int, input().split())
        graph[x-1][y-1] = 1
        graph[y-1][x-1] = 1
    
    count = 0
    for i in range(N):
        for j in range(i, N):
            for k in range(j, N):
                if is_triangle(graph, i, j, k):
                    count += 1

    answer.append(count)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



