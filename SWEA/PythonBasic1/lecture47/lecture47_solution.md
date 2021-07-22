```python
example = [1, 2, '4', 3]
checkerror = 0
result = 1
for i in example:
    if type(i) != type(123):
        checkerror = 1
        break
    else:
        result *= i

if checkerror:
    print("에러발생")
else:
    print(result)
```



