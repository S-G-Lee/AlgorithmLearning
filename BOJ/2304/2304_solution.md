```python
N = int(input())
cargo = [0] * 1001
for _ in range(N):
    l, h = map(int, input().split())
    cargo[l] = h

max_height = max(cargo)
max_position = cargo.index(max_height)
roof = [0] * 1001
cur_roof = 0
for i in range(max_position+1):
    if cur_roof < cargo[i]:
        cur_roof = cargo[i]
    roof[i] = cur_roof

cur_roof = 0
for i in range(1000, max_position, -1):
    if cur_roof < cargo[i]:
        cur_roof = cargo[i]
    roof[i] = cur_roof

result = sum(roof)
print(result)
```



