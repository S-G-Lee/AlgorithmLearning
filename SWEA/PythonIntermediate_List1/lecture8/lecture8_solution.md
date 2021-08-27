```python
casenum = int(input())

for case in range(1, casenum+1):
    
    N = int(input())
    cardlist = list(map(int, list(input())))
    cardcount = [0 for i in range(10)] # count each amount of number in cardlist, index = counting number
    
    for i in cardlist:
        cardcount[i] += 1
    
    maxcount = max(cardcount)
    maxnum = (9 - cardcount[::-1].index(maxcount))
    
    print(f'#{case} {maxnum} {maxcount}')
   
```



