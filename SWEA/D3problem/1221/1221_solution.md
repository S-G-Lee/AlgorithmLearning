```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    nothing, N = input().split()

    numbers = list(input().split())

    realnumbers = []
    for n in numbers:
        if n == "ZRO":
            realnumbers.append(0)
        elif n == "ONE":
            realnumbers.append(1)
        elif n == "TWO":
            realnumbers.append(2)
        elif n == "THR":
            realnumbers.append(3)
        elif n == "FOR":
            realnumbers.append(4)
        elif n == "FIV":
            realnumbers.append(5)            
        elif n == "SIX":
            realnumbers.append(6)
        elif n == "SVN":
            realnumbers.append(7)
        elif n == "EGT":
            realnumbers.append(8)
        elif n == "NIN":
            realnumbers.append(9)
    
    realnumbers.sort()

    new_numbers = []
    for n in realnumbers:
        if n == 0:
            new_numbers.append("ZRO")
        elif n == 1:
            new_numbers.append("ONE")
        elif n == 2:
            new_numbers.append("TWO")
        elif n == 3:
            new_numbers.append("THR")
        elif n == 4:
            new_numbers.append("FOR")
        elif n == 5:
            new_numbers.append("FIV")
        elif n == 6:
            new_numbers.append("SIX")
        elif n == 7:
            new_numbers.append("SVN")
        elif n == 8:
            new_numbers.append("EGT")
        elif n == 9:
            new_numbers.append("NIN")

    result = ' '.join(new_numbers)

    answer.append(result)    

for tc in range(1, T+1):
    # print(f'#{tc} {answer[tc-1]}')
    print(f'#{tc}')
    print(f'{answer[tc-1]}')
```



