```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, K = map(int, input().split())

    numbers = list(range(1, N+1))

    # dp[i][j] : 1 ~ i의 숫자의 집합 중 합이 j인 부분집합의 개수
    dp = [[0 for _ in range((N*(N+1)//2)+1)] for _ in range(N+1)]
    dp[0][0] = 1

    for i in range(1, N+1):
        dp[i][0] = 1
        max_sum = i*(i+1)//2
        for j in range(1, max_sum+1):
            if j < i:                
                dp[i][j] = dp[i-1][j]
            else:
                dp[i][j] = dp[i-1][j] + dp[i-1][j-i]

    result = dp[N][K]
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



