```python
T = int(input())

for tc in range(1, T + 1):

    numbers = list(map(int, input().split()))

    minimum = min(numbers)
    maximum = max(numbers)

    midavg = round((sum(numbers) - minimum - maximum) / (len(numbers) - 2))

    print(f'#{tc} {midavg}')
```



