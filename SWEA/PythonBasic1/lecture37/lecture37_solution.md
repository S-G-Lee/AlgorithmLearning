```python
def Fibonacci(n) : 
    if n == 0 or n == 1:
        return 1
    else :
        return Fibonacci(n-1) + Fibonacci(n-2)
        

T = int(input())

result = ""
for i in range(0,T) : 
    result = result + str(Fibonacci(i)) + ", "
result = result[:-2]
print("[" + result + "]")
```



