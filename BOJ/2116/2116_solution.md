```python
def set_dice_side(dice, bottom):
    bottom_idx = 0
    for i in range(6):
        if dice[i] == bottom:
            bottom_idx = i
            break
    top = 0
    if bottom_idx == 0:
        top = dice[5]
        dice[0] = 0
        dice[5] = 0
    elif bottom_idx == 1:
        top = dice[3]
        dice[1] = 0
        dice[3] = 0
    elif bottom_idx == 2:
        top = dice[4]
        dice[2] = 0
        dice[4] = 0
    elif bottom_idx == 3:
        top = dice[1]
        dice[1] = 0
        dice[3] = 0
    elif bottom_idx == 4:
        top = dice[2]
        dice[2] = 0
        dice[4] = 0
    elif bottom_idx == 5:
        top = dice[0]
        dice[0] = 0
        dice[5] = 0
    
    return max(dice), top
    

N = int(input())
dice_input = []
for i in range(N):
    dice_input.append(list(map(int, input().split())))
# 0-5 1-3 2-4

result = 0
for i in range(1, 7):
    dice = [[j for j in dice_input[x]] for x in range(N)]
    side_sum = 0
    bottom = i
    for j in range(N):
        side, bottom = set_dice_side(dice[j], bottom)
        side_sum += side
    if result < side_sum:
        result = side_sum

print(result)
```



