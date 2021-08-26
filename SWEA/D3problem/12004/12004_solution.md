```python
T = int(input())

for tc in range(1, T + 1): 

    num = int(input())

    result = 'No'
    for i in range(1, 10):
        for j in range(1, 10):
            if num == i * j:
                result = 'Yes'
                break
        if result == 'Yes':
            break
    
    print(f'#{tc} {result}')
```



