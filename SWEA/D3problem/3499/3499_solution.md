```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    
    words = input().split()
    amount = len(words)

    deck1 = words[:(amount+1)//2]
    deck2 = words[(amount+1)//2:]

    for i in range(amount):
        if i % 2 == 0:
            words[i] = deck1[i//2]
        else:
            words[i] = deck2[(i-1)//2]
    
    result = ' '.join(words)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



