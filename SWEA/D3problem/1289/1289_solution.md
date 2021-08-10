```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    bits = input()

    count = 0
    compare = '0'
    for bit in bits:
        if bit != compare:
            compare = bit
            count += 1
    
    result = count

    answer.append(result)
    
for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



