```python
import random


def cost(T):
    
    return T * 2 * random.random()


def annealing(Temperature, Temperature_end, k):

    infinite = 10000000
    cost_prev = infinite  # 이전 비용

    e = 2.718281828459045
    count = 0

    while Temperature > Temperature_end:          # T_end가 될 때까지 반복

        cost_new = cost(Temperature)      # 비용 계산

        diff = cost_new - cost_prev    # 새로운 비용과 이전 비용의 차이
        
        if diff < 0 or e**(-diff/Temperature) > random.random():

            cost_prev = cost_new    # 비용이 감소하거나 확률이 랜덤 값보다 더 크면 비용 갱신

        Temperature = Temperature * k                 # k : cooling factor
        count += 1

    return count


T = int(input())

answer = []
for tc in range(1, T + 1):

    Temperature, Temperature_end, k = map(float, input().split())

    result = annealing(Temperature, Temperature_end, k)

    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



