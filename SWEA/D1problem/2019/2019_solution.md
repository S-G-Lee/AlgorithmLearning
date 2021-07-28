```python
T = int(input())

result = ''
for i in range(T+1):
    result = result + str(2 ** i) + ' '
result = result[:-1]

print(result)
```



