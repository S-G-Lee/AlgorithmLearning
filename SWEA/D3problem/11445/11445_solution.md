```python
T = int(input())

for tc in range(1, T + 1): 

    P = input().strip()
    Q = input().strip()

    result = 'N'

    idx_p = 0
    idx_q = 0

    while idx_p < len(P):
        if P[idx_p] == Q[idx_q]:
            idx_p += 1
            idx_q += 1
            continue
        else:
            result = 'Y'
            break
    
    if result == 'N':
        if P != Q:
            result = 'Y'
            if len(P) < 10:
                if len(Q) == len(P) + 1:
                    if Q[-1] == 'a':
                        result = 'N'

    print(f'#{tc} {result}')
```



