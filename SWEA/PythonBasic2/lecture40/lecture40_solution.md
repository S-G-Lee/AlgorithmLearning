```python
#inputstr = input()
#while inputstr:
#    print('>> ' + inputstr.upper())
#    inputstr = input()

inputstr = input()
tmpchk = 0
while inputstr:
    print('>> ' + inputstr.upper())
    tmpchk += 1
    if tmpchk >= 3:
        break
    inputstr = input()
```



