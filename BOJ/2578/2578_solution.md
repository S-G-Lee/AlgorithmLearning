```python
bingo = []
for _ in range(5):
    bingo.append(list(map(int, input().split())))

numbers = []
for _ in range(5):
    numbers += list(map(int, input().split()))

count = 0
result = 0
for i in range(len(numbers)):
    check = 0
    for j in range(5):
        for k in range(5):
            if bingo[j][k] == numbers[i]:
                bingo[j][k] = 100
                if bingo[j][0] == bingo[j][1] == bingo[j][2] == bingo[j][3] == bingo[j][4] == 100:
                    count += 1
                if bingo[0][k] == bingo[1][k] == bingo[2][k] == bingo[3][k] == bingo[4][k] == 100:
                    count += 1
                if j == k:
                    if bingo[0][0] == bingo[1][1] == bingo[2][2] == bingo[3][3] == bingo[4][4] == 100:
                        count += 1
                if j == 4-k:
                    if bingo[0][4] == bingo[1][3] == bingo[2][2] == bingo[3][1] == bingo[4][0] == 100:
                        count += 1
                check = 1
                break
        if check > 0:
            break
    if count >= 3:
        result = i + 1
        break

print(result)
```



