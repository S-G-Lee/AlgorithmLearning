```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B, C = map(int, input().split())

    if A < B:
        result = C // A
    else:
        result = C // B
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



