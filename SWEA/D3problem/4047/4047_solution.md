```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    # S D H C order
    word = input()
    card_count = [[0 for _ in range(13)] for _ in range(4)]
    card_list = list(map(lambda i:word[i:i+3], range(0, len(word), 3)))
    pattern_list = 'SDHC'

    result = ''
    for card in card_list:
        pattern = pattern_list.index(card[0])
        idx = int(card[1:3]) - 1
        if card_count[pattern][idx] == 0:
            card_count[pattern][idx] += 1
        else:
            result = 'ERROR'
            break
    
    if result != 'ERROR':

        count = [13, 13, 13, 13]
        for i in range(len(card_count)):
            for j in range(len(card_count[i])):
                count[i] -= card_count[i][j]

        result = ' '.join(map(str, count))

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



