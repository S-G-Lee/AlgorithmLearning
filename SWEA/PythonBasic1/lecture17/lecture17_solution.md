```python
T = input()

if T.islower() :
    print("%s(ASCII: %d) => %s(ASCII: %d)" % (T, ord(T), chr(ord(T)-32), ord(T)-32))
else :
    print("%s(ASCII: %d) => %s(ASCII: %d)" % (T, ord(T), chr(ord(T)+32), ord(T)+32))
```



