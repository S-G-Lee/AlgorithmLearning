```python
T = int(input())

for tc in range(1, T+1):

    sentence = input()
    patern = ''

    idx1 = 0
    idx2 = 1

    while True:

        if sentence[idx1] == sentence[idx2]:

            tmpidx1 = idx1
            tmpidx2 = idx2
            chk = 1
            while tmpidx1 < idx2:

                if sentence[tmpidx1] != sentence[tmpidx2]:
                    chk = 0
                    break

                tmpidx1 += 1
                tmpidx2 += 1

            if chk:
                patern = sentence[idx1:idx2]
                break
        
        idx2 += 1

    print(f'#{tc} {len(patern)}')
```



