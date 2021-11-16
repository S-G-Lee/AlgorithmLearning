```python
N, K = map(int, input().split())

binary = bin(N)[2:]

result = binary

if binary.count('1') <= K:
    result = 0
else:
    new_n = N+1
    while True:
        new_binary = bin(new_n)[2:]
        if new_binary.count('1') <= K:
            result = new_n - N
            break
        new_n += 1

print(result)
```



