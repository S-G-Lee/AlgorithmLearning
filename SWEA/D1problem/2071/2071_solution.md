```python
T = int(input())

for tc in range(1, T+1):
    
    numberlist = list(map(int, input().split()))
    
    avg = 0
    for i in numberlist:
        avg += i
    avg = avg / len(numberlist)
    
    print(f'#{tc} {avg:.0f}')
```



