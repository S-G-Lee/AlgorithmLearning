```python
T = int(input())

for tc in range(1, T + 1):
    
    N = int(input())
    price_list = list(map(int, input().split()))
    price_day_log = [-1] * 10001 # price_day_log[price] = (last day that has come out), 10001 : price range size, -1 means 'no data'

    for day in range(len(price_list)):
        price_day_log[price_list[day]] = day
    
    pivot = 0
    maxprice = len(price_day_log) - 1
    total = 0
    while maxprice >= 0:

        if price_day_log[maxprice] >= 0:

            pivot2 = price_day_log[maxprice]

            if pivot <= pivot2:

                for i in range(pivot, pivot2 + 1):
                    total += maxprice - price_list[i]

                pivot = pivot2 + 1

        maxprice -= 1

    print(f'#{tc} {total}')
```



