```python
T = int(input())

for tc in range(1, T + 1): 

    N = int(input())
    numbers = list(map(int, input().split()))

    count = 0
    for i in range(1, N-1):
        if numbers[i-1] < numbers[i]:
            if numbers[i] < numbers[i+1]:
                count += 1
        elif numbers[i-1] > numbers[i]:
            if numbers[i] > numbers[i+1]:
                count += 1
    
    print(f'#{tc} {count}')
```



