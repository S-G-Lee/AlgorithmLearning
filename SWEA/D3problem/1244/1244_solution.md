```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    number, swap = map(int, input().split())
    digit = list(map(int, str(number)))

    i = 0
    check2 = 0
    while swap > 0:
        check = 0
        maxval = 0
        while True:
            maxval = max(digit[i:])
            if digit[i] < maxval:
                check = 1
                break
            elif i == len(digit)-2:
                break
            i += 1

        if check:
            count = 0
            backgroup = []
            for j in range(len(digit)-1,i-1,-1):
                if digit[j] == maxval:
                    count += 1
                    backgroup.append([j, digit[j]])
            count_front = digit[i:i+count].count(maxval)
            
            frontgroup = []
            for j in range(i, i+count):
                if digit[j] < maxval:
                    frontgroup.append([j, digit[j]])

            if swap < len(frontgroup):
                frontgroup = frontgroup[:swap]

            frontgroup.sort(key=lambda x:x[1])
            for j in range(len(frontgroup)):
                digit[frontgroup[j][0]], digit[backgroup[j][0]] = digit[backgroup[j][0]], digit[frontgroup[j][0]]
                swap -= 1  

        else:
            if tc == 10:
                oqwihtqo=0
            if check2 == 0:
                for j in range(len(digit)):
                    for k in range(j+1, len(digit)):
                        if digit[j] == digit[k]:
                            check2 = 2
                            break
                    if check2 == 2:
                        break
                if check2 != 2:
                    check2 = 1
                    
            if check2 == 2:
                pass
            else:
                digit[-2], digit[-1] = digit[-1], digit[-2]
            swap -= 1

    result = ''.join(map(str, digit))

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



