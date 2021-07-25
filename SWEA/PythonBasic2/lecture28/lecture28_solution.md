```python
import operator

inputdict  = {
"TV": 2000000,
"냉장고": 1500000,
"책상": 350000,
"노트북": 1200000,
"가스레인지": 200000,
"세탁기": 1000000
}

resultdict = dict(sorted(inputdict.items(), key = operator.itemgetter(1), reverse = True))

for key, val in resultdict.items():
    print(f"{key}: {val}")
```



