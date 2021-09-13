```python
T = 10

answer = []
for tc in range(1, T + 1):

    N = int(input())
    seq = input()

    stack = []
    digits = '0123456789'
    operator_outer = {
        '+': 1,
        '*': 2,
        '(': 3
    }
    operator_inner = {
        '(': 0,
        '+': 1,
        '*': 2,
    }
    
    postfix = ''
    for i in seq:
        if i in digits:
            postfix += i
        elif i == ')':
            while len(stack) > 0 and operator_inner[stack[-1]] != 0:
                postfix += stack.pop()
            stack.pop()
        else:
            while len(stack) > 0 and operator_outer[i] <= operator_inner[stack[-1]]:
                postfix += stack.pop()
            stack.append(i)            
	while stack:
        postfix += stack.pop()
        
    for i in postfix:
        if i in digits:
            stack.append(int(i))
        else:
            if i == '+':
                b = stack.pop()
                a = stack.pop()
                stack.append(a + b)
            else:
                b = stack.pop()
                a = stack.pop()
                stack.append(a * b)

    result = stack[-1]
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



