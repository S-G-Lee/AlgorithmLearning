문제

```
임의의 양의 정수를 입력받아 그 정수의 모든 약수를 구하십시오
```

답

```python
import sys
sys.stdin = open("input.txt", "r")

T = int(input())

for i in range(1, T+1):
    if T%i == 0:
        print("%d(은)는 %d의 약수입니다." % (i,T))
```

