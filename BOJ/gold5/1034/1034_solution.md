```python
N, M = map(int, input().split())

ramp = {}
for _ in range(N):
    temp = input()
    if temp not in ramp:
        ramp[temp] = 1
    else:
        ramp[temp] += 1
K = int(input())

result = 0
for state, num in ramp.items():
    zero_count = state.count('0')
    if K >= zero_count:
        if (K-zero_count) % 2 == 0:
            if result < num:
                result = num

print(result)
```



