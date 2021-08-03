```python
T = int(input())

for tc in range(1, T + 1):

    N = int(input())
    zipfile = []
    for _ in range(N):
        line = input().split()
        zipfile.append([line[0], int(line[1])])

    result = ''
    idx = 0
    for char, num in zipfile:
        count = 0
        while count < num:
            result += char
            idx += 1
            count += 1
            if idx >= 10: # max letter per line
                result += '\n'
                idx = 0
    
    print(f'#{tc} ')
    print(result)
```



