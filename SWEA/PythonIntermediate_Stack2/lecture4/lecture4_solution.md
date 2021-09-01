```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    input_list = input().split()

    stack = []
    result = 'error'
    try:
        for symbol in input_list:

            if symbol in '+-*/':
                b = int(stack.pop())
                a = int(stack.pop())
                if symbol == '+':
                    c = a + b
                elif symbol == '-':
                    c = a - b
                elif symbol == '*':
                    c = a * b
                else:
                    c = a // b
                stack.append(c)
            elif symbol == '.':
                result = int(stack.pop())
                if len(stack) != 0:
                    result = 'error'
                break
            else:
                stack.append(symbol)
    except:
        pass

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



