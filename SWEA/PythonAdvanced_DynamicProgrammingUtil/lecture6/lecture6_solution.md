```python
from itertools import combinations


def TSP_DP(N, graph):

    dp = [{} for _ in range(N)]

    for k in range(N-1):
        if k == 0:
            temp = tuple()
            for i in range(1, N):
                dp[i][temp] = graph[i][0]
        else:
            for i in range(1, N):
                full_list = list(range(1, N))
                full_list.remove(i)
                subset_group = list(combinations(full_list, k))
                for subset in subset_group:
                    key = subset
                    dp[i][key] = 100000
                    for v in subset:
                        subsubset = list(subset)[:]
                        subsubset.remove(v)
                        subkey = tuple(subsubset)
                        if dp[i][key] > graph[i][v] + dp[v][subkey]:
                            dp[i][key] = graph[i][v] + dp[v][subkey]

    subset = list(range(1, N))
    key = tuple(subset)
    dp[0][key] = 100000
    for v in subset:
        subsubset = list(subset)[:]
        subsubset.remove(v)
        subkey = tuple(subsubset)
        if dp[0][key] > graph[0][v] + dp[v][subkey]:
            dp[0][key] = graph[0][v] + dp[v][subkey]

    return dp[0][key]

T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    graph = [list(map(int, input().split())) for _ in range(N)]

    result = TSP_DP(N, graph)
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



