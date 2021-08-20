```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    numbers = list(map(int, input().split()))

    for i in range(1, N):

        if numbers[i-1] > 0 and numbers[i-1] + numbers[i] > 0:
            numbers[i] += numbers[i-1]

    result = max(numbers)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



