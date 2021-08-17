```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    word = input()

    result = 'Exist'
    while word:
        if word[0] == '*' or word[-1] == '*':
            break
        elif word[0] != word[-1]:
            result = 'Not exist'
            break
        word = word[1:-1]

    answer.append(result)
    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



