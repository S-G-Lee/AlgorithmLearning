```python
T = 10

answer = []
for tc in range(1, T + 1):

    V, E = map(int, input().split())

    nodes = list(map(int, input().split()))

    graph = [[0 for _ in range(V)] for _ in range(V)]
    visited = [0 for _ in range(V)]
    visited_count = 0
    possible = []
    link_count = [0 for _ in range(V)]

    for i in range(E):
        graph[nodes[2*i]-1][nodes[2*i+1]-1] = 1
        link_count[nodes[2*i+1]-1] += 1

    result = []
    while visited_count < V:

        for i in range(V):
            if not visited[i]:
                if link_count[i] == 0:
                    possible.append(i)

        for v in possible:
            visited[v] = 1
            visited_count += 1
            result.append(v+1)
            for i in range(V):
                if graph[v][i] == 1:
                    link_count[i] -= 1
        
        possible = []
    
    result = ' '.join(map(str, result))

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



