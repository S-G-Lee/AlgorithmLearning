```python
T = int(input())

for tc in range(1, T+1):
    
    date = input()
    year = date[:4]
    month = date[4:6]
    day = date[6:8]
    
    chk = 0
    
    if month in ['01', '03', '05', '07', '08', '10', '12']:
        if 1 <= int(day) <= 31:
            chk = 1
    elif month in ['04', '06', '09', '11']:
        if 1 <= int(day) <= 30:
            chk = 1
    elif month == '02':
        if 1 <= int(day) <= 28:
            chk = 1
    if chk:
        print(f'#{tc} {year}/{month}/{day}')
    else:
        print(f'#{tc} -1')
```



