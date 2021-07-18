```python
T = int(input())

primecounter = 0
for i in range(1,T+1):
    if T%i == 0 :
        print("%d(은)는 %d의 약수입니다." % (i, T))
        primecounter += 1
    if primecounter == 2 :
        print("%d(은)는 1과 %d로만 나눌 수 있는 소수입니다." % (T ,T))
```



