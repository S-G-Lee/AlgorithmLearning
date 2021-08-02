```python
T = int(input())

result = ''

for i in range(1, T+1):

    number = str(i)
    chkclap = 0
    for digit in number:
        if digit in ['3', '6', '9']:
            chkclap = 1
            result += '-'

    if not chkclap:
        result += number
    
    result += ' '

result = result[:-1]
print(result)
```



