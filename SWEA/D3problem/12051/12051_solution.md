```python
T = int(input())

for tc in range(1, T + 1): 

    N, pd, pg = map(int, input().split())

    # pd = wd / D * 100
    # pg = wg / G * 100 

    result = 'Possible'
    if N < 100:
        check = 0
        for i in range(1,N+1):
            if (pd * i) % 100 == 0:
                check = 1
                break
        if not check:
            result = 'Broken'
    
    if result == 'Possible':
        if pg == 0:
            if pd > 0:
                result = 'Broken'
        elif pg == 100:
            if pd < 100:
                result = 'Broken'

    print(f'#{tc} {result}')
```



