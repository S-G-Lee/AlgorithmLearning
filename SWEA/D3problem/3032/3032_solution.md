```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B = map(int, input().split())

    reverse = 0
    if A < B:
        reverse = 1
        A, B = B, A
    #확장 유클리드 호제법    
    a, b = A, B
    quotient = []
    while True:
        r = a%b
        if r == 0:
            break
        quotient.append(a//b)
        a, b = b, r
    
    x = 1
    y = -1 * quotient[-1]
    for i in range(len(quotient)-2,-1,-1):
        x, y = (y, x + (y * (-1 * quotient[i])))

    if reverse == 1:
        x, y = y, x
    result = ' '.join(map(str, [x, y]))
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



