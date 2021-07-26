```python
inputstr = input()

uppercheck = "QWERTYUIOPASDFGHJKLZXCVBNM"
lowercheck = "qwertyuiopasdfghjklzxcvbnm"

uppernum = 0
lowernum = 0
for char in list(inputstr):
    if char in uppercheck:
        uppernum += 1
    elif char in lowercheck:
        lowernum += 1

print(f'UPPER CASE {uppernum}')
print(f'LOWER CASE {lowernum}')
```



