```python
T = int(input())

for tc in range(1, T + 1): 

    s = input()
    
    stack = [-1] * 10000
    top = -1

    for char in s:
        if char is stack[top]:
            stack[top] = -1
            top -= 1
        else:
            top += 1
            stack[top] = char
    
    print(f'#{tc} {top + 1}')
```



