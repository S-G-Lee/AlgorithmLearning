```python
casenum = int(input())

for case in range(1, casenum+1):
    
    amount = int(input())
    inputstr = input().split()
    numlist = list(map(int, inputstr))
    
    minnum = min(numlist)
    maxnum = max(numlist)
    
    print(f'#{case} {maxnum - minnum}')
```



