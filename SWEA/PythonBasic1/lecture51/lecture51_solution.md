```python
inputarr = [1,2,3,4,5,6,7,8,9,10]
even = list(filter(lambda x : x%2 == 0, inputarr))
square = list(map(lambda x : x*x, even))
print(square)
```



