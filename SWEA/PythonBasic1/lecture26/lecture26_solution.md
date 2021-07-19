```python
bloodtypearr = ['A', 'A', 'A', 'O', 'B', 'B', 'O', 'AB', 'AB', 'O']
atype = 0
otype = 0
btype = 0
abtype = 0
for bloodtype in bloodtypearr:
    if bloodtype == 'A' :
   		atype += 1
    if bloodtype == 'O' :
        otype += 1
    if bloodtype == 'B' :
        btype += 1
    if bloodtype == 'AB' :
        abtype += 1
print("{'A': %d, 'O': %d, 'B': %d, 'AB': %d}" % (atype, otype, btype, abtype))
```



