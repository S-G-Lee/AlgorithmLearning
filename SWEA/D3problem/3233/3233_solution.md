```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B = map(int, input().split())

    total = 0
    for i in range(A//B):
        total += (2 * i) + 1

    answer.append(total)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



