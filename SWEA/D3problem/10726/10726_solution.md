```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N, M = map(int, input().split())

    result = 'OFF'

    M = bin(M)[2:]

    check = 1
    if len(M) >= N:
        checkbit = M[-N:]
        for bit in checkbit:
            if bit == '0':
                check = 0
                break
    else:
        check = 0
    
    if check:
        result = 'ON'

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



