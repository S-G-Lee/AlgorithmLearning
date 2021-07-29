```python
T = int(input())

for tc in range(1, T+1):
    
    a, b = list(map(int, input().split()))
    quotient, remainder = divmod(a, b)
    print(f'#{tc} {quotient} {remainder}')
```



