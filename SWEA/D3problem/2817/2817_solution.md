```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, K = map(int, input().split())

    numbers = list(map(int, input().split()))

    number_count = [0] * 1001
    for i in numbers:
        number_count[i] += 1

    dp = [[0 for _ in range(K+1)] for _ in range(N+1)]
    for i in range(N+1):
        for j in range(K+1):
            if i == 0:
                dp[i][j] = 0
            else:
                if j == numbers[i-1]:
                    dp[i][j] = dp[i-1][j] + 1
                elif j-numbers[i-1] >= 0:
                    dp[i][j] = dp[i-1][j] + dp[i-1][j-numbers[i-1]]
                else:
                    dp[i][j] = dp[i-1][j]

    result = dp[N][K]

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



