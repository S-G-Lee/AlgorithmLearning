```python
def create_wheretogo(word):

    length = len(word)
    result = [0] * length
    for i in range(length):
        count = 1
        for j in range(i+1, length):
            if word[i] == word[j]:
                result[i] = count
                break
            count += 1
    return result        


def boyer_moore_KMP(word, sentence):
    w_len = len(word)
    s_len = len(sentence)
    occurences = []

    idx_to_go = create_wheretogo(word)

    s_idx = 0
    count = 0
    while s_idx + w_len - 1 < s_len:
        if s_idx >= 20:
            a=0
        temp_idx = w_len - 1
        i = w_len - 1
        while i >= 0:
            if word[i] == sentence[s_idx + temp_idx]:
                temp_idx -= 1
            elif idx_to_go[temp_idx] != 0:
                temp_idx += idx_to_go[temp_idx]
                continue
            i -= 1

        if temp_idx == -1:
            occurences.append(s_idx)
            count += 1
            temp_idx = w_len - 1
        s_idx += temp_idx + 1

    # result = s_len - ((w_len - 1) * count)
    # return result
    return occurences


def boyer_moore(word, sentence):
    w_len = len(word)
    s_len = len(sentence)
    occurences = []

    s_idx = 0
    count = 0
    while s_idx + w_len - 1 < s_len:
        temp_idx = w_len - 1
        i = w_len - 1
        while i >= 0:
            if word[i] == sentence[s_idx + temp_idx]:
                temp_idx -= 1
            elif temp_idx != w_len - 1:
                temp_idx = w_len - 1
                continue
            i -= 1

        if temp_idx == -1:
            occurences.append(s_idx)
            count += 1
            temp_idx = w_len - 1
        s_idx += temp_idx + 1

    # result = s_len - ((w_len - 1) * count)
    # return result
    return occurences


def brute_force(word, sentence):
    w_len = len(word)
    s_len = len(sentence)
    occurences = []

    count = 0
    i = 0
    while i < s_len-w_len+1:
        for j in range(w_len):
            if word[j] != sentence[i+j]:
                break
        else:
            occurences.append(i)
            count += 1
            i += w_len
            continue
        i += 1
    # result = s_len - ((w_len - 1) * count)
    # return result
    return occurences

def make_skip_list(pattern):
    skip_list = [0]*len(pattern)
    # ex) TCTA: [3, 2, 1, 0]
    for idx, char in enumerate(pattern):
        skip_list[idx] = len(pattern) - idx - 1
    return skip_list

# ?????? ?????? ??????(bad character rule) ??????
def bad_char_rule(pattern, mismatched_idx, mismatched_char):
    skip_list = make_skip_list(pattern)
    shift = 0
    for i in range(len(pattern)-1, -1, -1):
        if pattern[i] == mismatched_char:
            shift = skip_list[i]
            break
    else:
        shift = len(pattern)
    return shift

# ????????? ?????? ?????? ??????
def boyer_moore_prof(string, pattern):
    i = 0 # ?????? ????????? ??????
    occurences = [] # ????????? ???????????? ?????? ??????
    while i <= len(string) - len(pattern):
        shift = 1
        mismatched = False
        # ??????????????? ???????????? ?????? ?????? ??????
        for j in range(len(pattern)-1, -1, -1):
            if string[i+j] != pattern[j]:
                shift_bc = bad_char_rule(pattern, j, string[i+j])
                shift = max(shift, shift_bc)
                mismatched = True
                break
        if not mismatched:
            shift = len(pattern)
            occurences.append(i)
        i += shift
    # result = len(string) - ((len(pattern) - 1) * len(occurences))
    # return result
    return occurences


T = int(input())

answer = []
for tc in range(1, T + 1):

    sentence, word = input().split()

    result1 = boyer_moore_KMP(word, sentence)
    # result2 = brute_force(word, sentence)
    # result3 = boyer_moore_prof(sentence, word)

    a = len(sentence) - ((len(word) - 1) * len(result1))
    # b = len(sentence) - ((len(word) - 1) * len(result2))
    # c = len(sentence) - ((len(word) - 1) * len(result3))

    answer.append(a)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



