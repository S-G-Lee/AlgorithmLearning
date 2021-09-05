```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    num = float(input())

    digit = 1/2
    result = ''
    for _ in range(12):
        if num > digit:
            num = num-digit
            result += '1'
        elif num < digit:
            result += '0'
        else:
            result += '1'
            break
        digit = digit / 2
    else:
        result = 'overflow'
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



