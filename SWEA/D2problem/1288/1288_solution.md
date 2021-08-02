```python
T = int(input())

for tc in range(1, T + 1): 

    N = int(input())

    number_checked = [False for _ in range(10)]
    count = 0

    result = N

    while count < 10:

        N_str = str(result)
        for n in N_str:
            if not number_checked[int(n)]:
                number_checked[int(n)] = True
                count += 1
        
        if count >= 10:
            break
        result += N
    
    print(f'#{tc} {result}')
```



