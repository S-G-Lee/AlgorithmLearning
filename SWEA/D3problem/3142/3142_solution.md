```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())

    a = N - M
    b = (2 * M) - N

    result = ' '.join(map(str, [b, a]))

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



