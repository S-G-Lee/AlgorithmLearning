```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    word = input()
    rev = word[::-1]

    result = ''
    for char in rev:
        if char == 'b':
            result += 'd'
        if char == 'd':
            result += 'b'
        if char == 'q':
            result += 'p'
        if char == 'p':
            result += 'q'

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



