```python
T = 10

answer = []
for tc in range(1, T + 1):

    nothing = input()
    seg = input()
    sentence = input()
    result = sentence.count(seg)

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



