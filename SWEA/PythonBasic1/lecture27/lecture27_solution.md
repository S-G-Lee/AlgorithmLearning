```python
scorearr = [85, 65, 77, 83, 75, 22, 98, 88, 38, 100]
idx = 0
while idx<len(scorearr) : 
    if scorearr[idx] < 80 : 
    	scorearr.pop(idx)
    else : 
        idx += 1

result = 0
for i in scorearr : 
    result += i
print(result)
    

```



