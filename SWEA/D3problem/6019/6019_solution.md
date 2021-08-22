```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    D, A, B, F = map(int, input().split())

    total = 0

    check = 1
    while D > 0.000001:
        if check:
            check = 0
            total += D * (F/(F+B))
            D = D /(F+B) * (F - A)
        else:
            check = 1
            total += D * (F/(F+A))
            D = D /(F+A) * (F - B)

    answer.append(total)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]:.10f}')
```



