```python
fruit = ['   apple    ','banana','  melon']

fruitdict = { name.replace(' ','') : len(name.replace(' ','')) for name in fruit }

print(fruitdict)
```



