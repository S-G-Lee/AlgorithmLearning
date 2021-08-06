```python
T = int(input())

for tc in range(1, T + 1):

    word = input()
    reverse = word[::-1]
     
    result = 0
    if word == reverse:
        result = 1

    print(f'#{tc} {result}')

```



