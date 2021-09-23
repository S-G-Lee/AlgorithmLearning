```python
N = int(input())

max_length = 0
final_second = 0
for i in range(1, N + 1):
    first = N
    second = i    
    count = 2
    while first - second >= 0:
        count += 1
        first, second = second, first - second
    
    if max_length < count:
        max_length = count
        final_second = i

print(max_length)
first = N
second = final_second
result = [first, second]
while first - second >= 0:
    result.append(first - second)
    first, second = second, first - second 
result = ' '.join(map(str, result))
print(result)
```



