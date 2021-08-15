```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    L, U, X = map(int, input().split())

    result = 0

    if X > U:
        result = -1
    elif X < L:
        result = L - X

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



