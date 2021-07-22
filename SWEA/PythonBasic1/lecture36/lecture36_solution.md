```python
def CheckPrime(num) : 
    for i in range(2, num) : 
        if num%i == 0:
            return False
    return True

T = int(input())
result = CheckPrime(T)
if result : 
    print("소수입니다.")
else : 
    print("소수가 아닙니다.")

```



