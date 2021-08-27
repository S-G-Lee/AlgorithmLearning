```python
casenum = int(input())

for case in range(1, casenum+1):
    
    N, M = list(map(int, input().split()))
    numberlist = list(map(int, input().split()))
    
    sumlist = [0] * (N-M+1) #list that save sum of each subarray
    for i in range(N-M+1):
        sum = 0
        for j in numberlist[i:i+M]:
            sum += j
        sumlist[i] = sum
    
    print(f'#{case} {max(sumlist)-min(sumlist)}')
```



