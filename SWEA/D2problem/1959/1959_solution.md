```python
T = int(input())

for tc in range(1, T + 1):

    N, M = list(map(int, input().split()))

    numbers1 = list(map(int, input().split()))
    numbers2 = list(map(int, input().split()))

    if N > M:
        numbers1, numbers2 = numbers2, numbers1
        N, M = M, N

    len1 = len(numbers1)
    len2 = len(numbers2)

    result = 0
    for i in range(len2 - len1 + 1):
        total = 0
        for j in range(len1):
            total += numbers1[j] * numbers2[i+j]
        if result < total:
            result = total
    
    print(f'#{tc} {result}')
```



