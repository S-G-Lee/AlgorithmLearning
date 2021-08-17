```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    word = input()

    result = ''
    for char in word:
        if char not in 'aeiou':
            result += char
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



