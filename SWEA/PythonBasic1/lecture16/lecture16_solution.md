```python
firstman = input()
secondman = input()

if firstman == "바위":
    if secondman == "가위":
        print("Result : Man1 Win!")
    elif secondman == "보":
        print("Result : Man2 Win!")
    else:
        print("Result : Draw")
elif firstman == "가위":
    if secondman == "보":
        print("Result : Man1 Win!")
    elif secondman == "바위":
        print("Result : Man2 Win!")
    else:
        print("Result : Draw")
else:
    if secondman == "바위":
        print("Result : Man1 Win!")
    elif secondman == "가위":
        print("Result : Man2 Win!")
    else:
        print("Result : Draw")
```



