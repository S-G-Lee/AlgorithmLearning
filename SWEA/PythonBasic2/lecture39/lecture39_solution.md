```python
inputwords = input().replace(':', '/').split('/')

resultwords = [i for i in inputwords if i]

print(f'protocol: {resultwords[0]}')
print(f'host: {resultwords[1]}')
print(f'others: {resultwords[2]}')
```



