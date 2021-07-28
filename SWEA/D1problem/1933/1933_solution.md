```python
N = int(input())

result = ''
for i in range(1, N+1):
    if not N % i:
        result = result + str(i) + ' '
result = result[:-1]

print(result)
```



