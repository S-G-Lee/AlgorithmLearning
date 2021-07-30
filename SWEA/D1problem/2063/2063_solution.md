```python
N = int(input())

numberlist = list(map(int, input().split()))

numberlist = sorted(numberlist)
idx = int((N - 1) / 2)

result = numberlist[idx]

print(result)
```



