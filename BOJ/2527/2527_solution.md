```python
for _ in range(4):

    inputs = list(map(int, input().split()))

    rec1 = []
    rec1.append([inputs[0], inputs[1]])
    rec1.append([inputs[2], inputs[3]])
    rec2 = []
    rec2.append([inputs[4], inputs[5]])
    rec2.append([inputs[6], inputs[7]])

    if rec1[0][0] > rec2[0][0]:
        rec1, rec2 = rec2, rec1

    result = 'd'
    if rec1[1][0] < rec2[0][0]:
        result = 'd'
    elif rec1[1][0] == rec2[0][0]:
        if rec1[1][1] < rec2[0][1]:
            result = 'd'
        elif rec1[1][1] == rec2[0][1]:
            result = 'c'
        else:
            if rec1[0][1] > rec2[1][1]:
                result = 'd'
            elif rec1[0][1] == rec2[1][1]:
                result = 'c'
            else:
                result = 'b'
    else:
        if rec1[1][1] < rec2[0][1]:
            result = 'd'
        elif rec1[1][1] == rec2[0][1]:
            result = 'b'
        else:
            if rec1[0][1] > rec2[1][1]:
                result = 'd'
            elif rec1[0][1] == rec2[1][1]:
                result = 'b'
            else:
                result = 'a'

    print(result)
```



