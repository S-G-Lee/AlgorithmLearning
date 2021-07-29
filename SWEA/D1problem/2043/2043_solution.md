```python
P, K = list(map(int, input().split()))

result = 0
if P > K:
    result = P - K + 1
else :
    result = K - P + 1

print(result)
```



