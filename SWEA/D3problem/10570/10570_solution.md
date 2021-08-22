```python
def is_pal(n):
    n = str(n)
    l = len(n)
    r = (l+1)//2
    for i in range(r):
        if n[i] != n[l-i-1]:
            return False
    return True
        

T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    A, B = map(int, input().split())

    count = 0

    sqrt_min = int((A-1) ** (1/2)) + 1
    sqrt_max = int(B ** (1/2))
    for i in range(sqrt_min, sqrt_max + 1):
        if is_pal(i):
            square = i*i
            if is_pal(square):
                count += 1
    
    answer.append(count)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



