```python
from itertools import combinations, product
from copy import deepcopy


def find_amount(D, W, K, film):

    if K == 1:
        return 0
        
    amount = 0
    while amount < K:
        # 몇 번째 열을 바꿀지 결정
        chemical_order_list = list(combinations(range(D), amount))
        # 위에서 정해진 열을 무슨 종류로 바꿀지 결정
        chemical_kind_list = list(product((0, 1), repeat=amount))
        for chemical_order in chemical_order_list:
            for chemical_kind in chemical_kind_list:
                for j in range(W):
                    temp = 2
                    count = 0
                    for i in range(D):
                        if i in chemical_order:
                            kind = chemical_kind[chemical_order.index(i)]
                        else:
                            kind = film[i][j]
                        if temp != 0 and kind == 0:
                            temp = 0
                            count = 1
                        elif temp != 1 and kind == 1:
                            temp = 1
                            count = 1
                        else:
                            count += 1                        
                            if count >= K:
                                break
                    else:
                        break
                else:
                    return amount
        amount += 1
    return K


T = int(input())

answer = []
for tc in range(1, T + 1):

    D, W, K = map(int, input().split())
    film = [list(map(int, input().split())) for _ in range(D)]

    result = find_amount(D, W, K, film)
                
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



