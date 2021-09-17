```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    n, a, b = map(int, input().split())

    dp = [[1 for _ in range(n+1)] for _ in range(n+1)]
    
    # nCr = n-1Cr-1 + n-1Cr
    for i in range(1, n+1):
        for j in range(1, i):
            dp[i][j] = dp[i-1][j-1] + dp[i-1][j]

    result = dp[n][a]
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



