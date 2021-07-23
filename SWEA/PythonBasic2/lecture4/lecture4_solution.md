```python
inputstr = list('Python is powerful... and fast; plays well with others; runs everywhere; is friendly & easy to learn; is Open.')
resultlist = [i for i in inputstr if i not in list('aeiou')]
resultstr = "".join(resultlist)
print(resultstr)
```



