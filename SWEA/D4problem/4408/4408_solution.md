```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    corridor = [0] * 201

    for _ in range(N):
        a, b = map(int, input().split())
        if a > b:
            a, b = b, a
        for i in range((a+1)//2, ((b+1)//2)+1):
            corridor[i] += 1

    result = max(corridor)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



