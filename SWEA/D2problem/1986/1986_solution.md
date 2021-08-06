```python
T = int(input())

for tc in range(1, T + 1):

    N = int(input())

    numbers = [i for i in range(1,N+1)]

    plus = sum(numbers[::2])
    if N > 1:
        minus = sum(numbers[1::2])
    else:
        minus = 0
    
    print(f'#{tc} {plus-minus}')
```



