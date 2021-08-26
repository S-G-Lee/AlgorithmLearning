```python
T = int(input())

for tc in range(1, T + 1): 

    node_list = input()

    a = 1
    b = 1

    for node in node_list:
        if node == 'L':
            b = a + b
        elif node == 'R':
            a = a + b

    print(f'#{tc} {a} {b}')
```



