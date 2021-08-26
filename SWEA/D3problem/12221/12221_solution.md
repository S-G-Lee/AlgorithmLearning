```python
T = int(input())

for tc in range(1, T + 1): 

    a, b = input().split()

    result = 0

    if len(a) > 1 or len(b) > 1:
        result = -1
    else:
        a = int(a)
        b = int(b)
        result = a * b
    
    print(f'#{tc} {result}')
```



