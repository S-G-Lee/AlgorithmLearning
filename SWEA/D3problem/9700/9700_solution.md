```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    p, q = map(float, input().split())

    # pq
    s1 = (1 - p) * (1 - q) * q
    s2 = p * (1 - q) *(1 - q) * q

    result = 'NO'
    if s1 < s2:
        result = 'YES'

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



