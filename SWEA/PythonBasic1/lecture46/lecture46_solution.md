```python
inputstr = "ADCBBBBCABBCBDACBDCAACDDDCAABABDBCBCBDBDBDDABBAAAAAAADADBDBCBDABADCADC"
charlist = ['A','B','C','D']

str_onechar = list(map( lambda x : list(filter(lambda y : y == x, inputstr)), charlist))

score = 0
for i in range(len(str_onechar)):
    score += (4-i)*len(str_onechar[i])
print(score)
```



