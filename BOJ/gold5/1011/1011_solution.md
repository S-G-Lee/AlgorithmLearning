```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    x, y = map(int, input().split())

    deaccelerate_start_pos = y-x

    speed = 1
    while deaccelerate_start_pos >= (y-x)/2:
        deaccelerate_start_pos -= speed
        speed += 1
    speed -= 1
    deaccelerate_start_pos += speed

    if deaccelerate_start_pos == (y-x)//2:
        result = 2 * speed - 2
    else:
        if (2 * deaccelerate_start_pos) - (y-x) <= speed:
            result = 2 * speed - 1
        else:
            result = 2 * speed
    
    print(result)
```



