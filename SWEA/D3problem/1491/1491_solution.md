```python
def weight(N, A, B, R, C):
    return A*abs(R-C) + B*(N-(R*C))

T = int(input())

answer = []
for tc in range(1, T + 1):

    N, A, B = map(int, input().split())
    
    min1 = 10000000000
    min2 = 10000000000

    i=0
    while True:
        w = weight(N, A, B, i, i)
        if w < 0:
            break
        min1 = min(min1, w)
        i += 1
    
    for i in range(int(N**(1/2)), 0, -1):
        w = weight(N, A, B, i, N//i)
        if w < 0:
            break
        min2 = min(min2, w)
    
    result = min(min1, min2)

    answer.append(result)
    
for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



