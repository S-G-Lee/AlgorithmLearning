```python
def sharp(a, b):
    n = a + b
    n = (n-1)*(n-2)//2
    n = n + a
    return n

def ampersand(n):
    stage = 1
    total = 0
    while total < n:
        total += stage
        stage += 1
    y = total - n + 1
    x = stage - (total - n + 1)
    return x, y

def star(p, q):
    x1, y1 = ampersand(p)
    x2, y2 = ampersand(q)
    n = sharp(x1+x2, y1+y2)
    return n


T = int(input())

answer = []
for tc in range(1, T + 1):

    p, q = map(int, input().split())

    result = star(p, q)

    answer.append(result)
    
for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



