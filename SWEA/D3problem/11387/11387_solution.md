```python
T = int(input())

for tc in range(1, T + 1): 

    D, L, N = map(int, input().split())

    n = 0
    total = 0
    
    for _ in range(N):        
        total += D + ((D//100) * n* L)
        n += 1
    
    print(f'#{tc} {total}')
```



