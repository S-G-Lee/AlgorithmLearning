```python
class Circle:
    
    def __init__(self):
        self.__radius = 2
    def getarea(self):
        return 3.14 * self.__radius *self.__radius
    
cir = Circle()
print(f"원의 면적: {cir.getarea()}")
```



