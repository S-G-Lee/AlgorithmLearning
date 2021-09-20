```python
N = int(input())

numbers = list(map(int, input().split()))

max_length = 0
prev = numbers[0]
inc_length = 0
dec_length = 0
for i in numbers:

    if prev < i:
        inc_length += 1
        if max_length < dec_length:
            max_length = dec_length
        dec_length = 1
    elif prev > i:
        dec_length += 1
        if max_length < inc_length:
            max_length = inc_length
        inc_length = 1
    else:
        inc_length += 1
        dec_length += 1
        
    prev = i

if max_length < max(inc_length, dec_length):
    max_length = max(inc_length, dec_length)

print(max_length)
```



