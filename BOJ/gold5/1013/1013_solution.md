```python
from collections import deque

import re



# pattern1: (100+1+)
def pattern1_possible(N, signal, i):
    if i < N - 3:
        if (signal[i] == '1') and (signal[i+1] == '0') and (signal[i+2] == '0'):
            temp = 3
            while signal[i+temp] == '0':
                temp += 1
                if i+temp >= N:
                    return 0
            while i+temp < N and signal[i+temp] == '1':
                temp += 1
            return temp
            
    return 0


# pattern2: (01)
def pattern2_possible(N, signal, i):
    if i < N - 1:
        if signal[i] == '0' and signal[i+1] == '1':
            return True
    return False


def check_signal(signal):
    q = deque()
    N = len(signal)
    q.append(0)
    while len(q) > 0:
        i = q.popleft()
        if i == N:
            return 'YES'
        temp = pattern1_possible(N, signal, i)
        if temp:
            q.append(i+temp)
        if pattern2_possible(N, signal, i):
            q.append(i+2)
    return 'NO'


# DFA(Determinstic Finite Automata), NFA(Nondeterminstic Finite Automata) 문제
T = int(input())

# pattern = (100+1+ | 01)+
for tc in range(1, T+1):
    signal = input()

    result = 'NO'
    # if signal[-1] == '1':
        # result = check_signal(signal)

    p = re.compile('(100+1+|01)+')

    m = p.fullmatch(signal)
    
    if m:
        result = 'YES'

    print(result)

```



