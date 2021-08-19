```python
def score_check(ingre_list, cur_ingre, N, L, score):
    if L < 0:
        return 0
    else:
        result = 0
        for i in range(cur_ingre + 1, N):
            cur_L = L - ingre_list[i][1]
            cur_score = ingre_list[i][0]
            tempscore = score_check(ingre_list, i, N, cur_L, cur_score)
            if result < tempscore:
                result = tempscore
        a = result + score
        return result + score

T = int(input())

answer = []
for tc in range(1, T + 1):

    N, L = map(int, input().split())
    ingredient_list = [] # has the number of list element [t, k], t means score and k means calorie
    for _ in range(N):
        ingredient_list.append(list(map(int, input().split())))
    
    result = score_check(ingredient_list, -1, N, L, 0)
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



