```python
casenum = int(input())

for case in range(1, casenum+1):
    
    numberlist = list(map(int, input().split()))
    
    sum = 0
    for i in numberlist:
        if i%2:
            sum += i
    
    print(f'#{case} {sum}')
```



