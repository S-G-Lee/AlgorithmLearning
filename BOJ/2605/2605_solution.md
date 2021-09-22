```python
N = int(input())

order = list(map(int, input().split()))

line = [0] * N

for i in range(N):
    line[i] = i + 1
    idx = i
    for _ in range(order[i]):
        line[idx], line[idx - 1] = line[idx - 1], line[idx]
        idx -= 1

result = ' '.join(map(str, line))
print(result)
```



