```python
T = int(input())
binary = ""
while T > 1 :
    binary = str(T%2) + binary
    T = T//2
binary = "1" + binary
print(binary)
```



