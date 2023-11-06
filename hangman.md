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
