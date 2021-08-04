```python
T = int(input())

for tc in range(1, T + 1):

    N = int(input())

    numbers = list(map(int, input().split()))

    for i in range(N):
        for j in range(i,N):
            if numbers[i] > numbers[j]:
                numbers[i], numbers[j] = numbers[j], numbers[i]

    result = ' '.join(map(str, numbers))

    print(f'#{tc} {result}')
```



