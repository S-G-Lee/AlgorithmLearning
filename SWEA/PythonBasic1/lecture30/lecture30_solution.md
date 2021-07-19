```python
T = input()

numbercount = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

for char in T : 
    idx = int(char)
    numbercount[idx] += 1
    
result = ""
for i in numbercount : 
    result = result + str(i) + " "

result = result[:-1]
print("0 1 2 3 4 5 6 7 8 9")
print(result)
```



