```python
T = int(input())

for tc in range(1, T+1):
    
    a, b = list(map(int, input().split()))
    result = '='
    if a < b:
        result = '<'
    elif a > b:
        result = '>'
    
    print(f'#{tc} {result}')
    
```



