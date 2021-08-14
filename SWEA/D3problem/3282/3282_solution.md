```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, K = map(int, input().split())

    knapsack = []
    for _ in range(N):
        knapsack.append(list(map(int, input().split())))
    
    dp = [[0 for _ in range(K+1)] for _ in range(N+1)]

    for i in range(0, N+1):
        for j in range(1, K+1):
            if i > 0:
                if knapsack[i-1][0] > j:
                    dp[i][j] = dp[i-1][j]
                else:
                    dp[i][j] = max(dp[i-1][j], dp[i-1][j-knapsack[i-1][0]] + knapsack[i-1][1])
    
    result = dp[N][K]

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



