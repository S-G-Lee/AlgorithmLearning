```python
N, M = map(int, input().split())

temperature = list(map(int, input().split()))

length = 1
tempsum = 0
result = -10000000
for i in range(N):
    if length < M:
        tempsum += temperature[i]
        length += 1
    else:
        tempsum += temperature[i]
        if result < tempsum:
            result = tempsum
        tempsum -= temperature[i-M+1]

print(result)

```



