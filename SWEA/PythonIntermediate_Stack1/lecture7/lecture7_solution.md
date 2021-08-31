```python
T = int(input())

for tc in range(1, T + 1): 

    string = input()

    stack = [0] * 10000
    top = 0

    for letter in string:
        if letter in ['(', '{']:
            top += 1
            stack[top] = letter
        elif letter is ')':
            if stack[top] == '(':
                stack[top] = 0
                top -= 1
            else:
                top = -1
                break
        elif letter is '}':
            if stack[top] == '{':
                stack[top] = 0
                top -= 1
            else:
                top = -1
                break
    
    result = 0
    if top == 0:
        result = 1
    print(f'#{tc} {result}')
```



