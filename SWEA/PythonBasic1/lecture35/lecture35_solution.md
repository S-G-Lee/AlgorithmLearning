```python
def Versus(a,b) :
    rspdict = {"바위" : 0, "가위" : 1, "보" : 2}
    anum = rspdict[a]
    bnum = rspdict[b]
    winner = ""
    if anum + bnum == 1 : 
        winner = "바위"
    elif anum + bnum == 2 : 
        winner = "보"
    else :
        winner = "가위"
    return winner

user1 = input()
user2 = input()
hand1 = input()
hand2 = input()

result = Versus(hand1, hand2)
print("%s가 이겼습니다!" % (result))

```



