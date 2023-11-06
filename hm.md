# hangman
```py
import random

words = ["animal", "banana", "fruit", "elemental"]
end_game = False
lives = 6

random_word = random.choice(words)

list = []
for letter in random_word:
    list += '_'
print(list)

while not end_game:
    a=input("알파벳을 입력하세요. : ").lower()
    if a in list:
        print("맞췄던 알파벳 입니다.")
        

    for index in range(len(random_word)):
        guess_letter = random_word[index]
        if guess_letter == a:
            list[index] = guess_letter
            print(list)
            
    if a not in list:
        print("틀렸습니다.")
        lives -= 1
        if lives == 0:
            end_game = True
            print("+----------+\nl          l\nl          o\nl         /l\ \nl         / \ \nl\nl\nl\n========")
            print("실패하였습니다.")
        if lives == 5:
            print("+----------+\nl          l\nl          o\nl\nl\nl\nl\nl\n========")
        if lives == 4:
            print("+----------+\nl          l\nl          o\nl          l\nl\nl\nl\nl\n========")
        if lives == 3:
            print("+----------+\nl          l\nl          o\nl         /l\nl\nl\nl\nl\n========")
        if lives == 2:
            print("+----------+\nl          l\nl          o\nl         /l\ \nl\nl\nl\nl\n========")
        if lives == 1:
            print("+----------+\nl          l\nl          o\nl         /l\ \nl         /\nl\nl\nl\n========")
        

    if '_' not in list:
        end_game = True
        print("이겼습니다.")
print(list)
```

# 결과1 (성공)
```py
['_', '_', '_', '_', '_']
알파벳을 입력하세요. : a
틀렸습니다.
+----------+
l          l
l          o
l
l
l
l
l
========
알파벳을 입력하세요. : b
틀렸습니다.
+----------+
l          l
l          o
l          l
l
l
l
l
========
알파벳을 입력하세요. : e
틀렸습니다.
+----------+
l          l
l          o
l         /l
l
l
l
l
========
알파벳을 입력하세요. : f
['f', '_', '_', '_', '_']
알파벳을 입력하세요. : r
['f', 'r', '_', '_', '_']
알파벳을 입력하세요. : u
['f', 'r', 'u', '_', '_']
알파벳을 입력하세요. : i
['f', 'r', 'u', 'i', '_']
알파벳을 입력하세요. : t
['f', 'r', 'u', 'i', 't']
이겼습니다.
['f', 'r', 'u', 'i', 't']
```
# 결과2(실패)
```py
['_', '_', '_', '_', '_', '_', '_', '_', '_']
알파벳을 입력하세요. : a
['_', '_', '_', '_', '_', '_', '_', 'a', '_']
알파벳을 입력하세요. : b
틀렸습니다.
+----------+
l          l
l          o
l
l
l
l
l
========
알파벳을 입력하세요. : c
틀렸습니다.
+----------+
l          l
l          o
l          l
l
l
l
l
========
알파벳을 입력하세요. : d
틀렸습니다.
+----------+
l          l
l          o
l         /l
l
l
l
l
========
알파벳을 입력하세요. : e
['e', '_', '_', '_', '_', '_', '_', 'a', '_']
['e', '_', 'e', '_', '_', '_', '_', 'a', '_']
['e', '_', 'e', '_', 'e', '_', '_', 'a', '_']
알파벳을 입력하세요. : f
틀렸습니다.
+----------+
l          l
l          o
l         /l\ 
l
l
l
l
========
알파벳을 입력하세요. : g
틀렸습니다.
+----------+
l          l
l          o
l         /l\ 
l         /
l
l
l
========
알파벳을 입력하세요. : h
틀렸습니다.
+----------+
l          l
l          o
l         /l\ 
l         / \ 
l
l
l
========
실패하였습니다.
['e', '_', 'e', '_', 'e', '_', '_', 'a', '_']
```
