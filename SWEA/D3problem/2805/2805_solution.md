```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    field = []
    for _ in range(N):
        field.append(list(map(int, input())))
    
    result = 0
    for i in range(N):
        for j in (range(abs((N//2)-i), N-abs((N//2)-i))):
            result += field[i][j]

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



