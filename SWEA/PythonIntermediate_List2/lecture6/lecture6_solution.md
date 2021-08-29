```python
def findsubsetamount(total, elementnum, startnum, endnum):

    num = 0
    if total >= startnum:
        for i in range(startnum, endnum):
            if elementnum == 1:
                if i == total:
                    num = 1
            else:
                num += findsubsetamount(total - i, elementnum - 1, i+1, endnum)

    return num


casenum = int(input())

for case in range(1, casenum+1):

    N, K = list(map(int, input().split()))

    result = findsubsetamount(K, N, 1, 13)

    print(f'#{case} {result}')
```



