```python
from collections import deque
    

T = int(input())

for tc in range(1, T+1):
    N, K = map(int, input().split())
    time = list(map(int, input().split()))
    indegree = [0] * N
    edges = [[] for _ in range(N)]
    for _ in range(K):
        v, w = map(int, input().split())
        w -= 1
        v -= 1
        edges[v].append(w)
        indegree[w] += 1
    accumulated_time = time[:]
    W = int(input())
    W -= 1

    q = deque()

    for i in range(N):
        if indegree[i] == 0:
            q.append(i)
    
    while len(q) > 0:
        v = q.popleft()
        if v == W:
            result = accumulated_time[v]
            break
        for w in edges[v]:
            indegree[w] -= 1
            if accumulated_time[w] < accumulated_time[v] + time[w]:
                accumulated_time[w] = accumulated_time[v] + time[w]
            if indegree[w] == 0:
                q.append(w)

    print(result)

```



