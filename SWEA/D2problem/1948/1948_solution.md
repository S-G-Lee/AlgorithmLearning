```python
T = int(input())

for tc in range(1, T + 1):

    m1, d1, m2, d2 = list(map(int, input().split()))
    # 1/31, 2/28, 3/31, 4/30, 5/31, 6/30, 7/31, 8/31, 9/30, 10/31, 11/30, 12/31
    days_list = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    
    year = []
    accumulated_date = 0
    for i in days_list:
        year.append([j + accumulated_date for j in range(1, i + 1)])
        accumulated_date += len(year[-1])
    
    date1 = year[m1-1][d1-1]
    date2 = year[m2-1][d2-1]

    print(f'#{tc} {date2 - date1 + 1}')
```



