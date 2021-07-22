```python
def Square(x) : 
    return x*x

T = input()
temparr = T.split(',')
inputarr = []
for i in temparr : 
    inputarr.append(int(i))
for i in inputarr :
    print("square(%d) => %d" % (i, Square(i)))

```



