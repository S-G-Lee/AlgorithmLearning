```python
T = int(input())

for tc in range(1, T+1):
    
    numberlist = list(map(int, input().split()))
    
    result = max(numberlist)
    
    print(f'#{tc} {result}')
```



