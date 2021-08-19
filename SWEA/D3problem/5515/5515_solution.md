```python
T = int(input())

days = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
week = [[0 for j in range(days[i])] for i in range(12)]
day = 4
for i in range(12):
    for j in range(days[i]):
        week[i][j] = day
        day = (day + 1) % 7

answer = []
for tc in range(1, T + 1):

    M, D = map(int, input().split())

    result = week[M-1][D-1]

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



