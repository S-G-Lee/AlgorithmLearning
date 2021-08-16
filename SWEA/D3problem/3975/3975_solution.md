```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B, C, D = map(int, input().split())

    result = ''
    if A*D > B*C:
        result = 'ALICE'
    elif A*D < B*C:
        result = 'BOB'
    else:
        result = 'DRAW'

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



