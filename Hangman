from random import seed
from random import randrange
from datetime import datetime

seed(datetime.now())

words = ["καλος", "ευειδης", "υπολογιστης", "καταστροφη", "λαμπα", "σομπα", "θαρραλεος", "ηχειο", "ανεμοστροβιλος",
         "μπουκαλι", "περνωντας", "βιβλιοθηκαριος", "πληροφορικη", "πανεπηστημιο", "προγραμματιστης"]
guessed_letters = []  # player's letters input
find = []  # "_" correlate with words
rounds = 1
max_rounds = 0  # player's wrongs

wordpos = randrange(15)  # a random word
hidden_word = words[wordpos]
word = list(hidden_word)  # separates the word to letters
for i in range(len(word)):  # initialization with "_" to correlate with word
    find.append("_")
while True:
    letter = input("Dwse ena gramma: ")
    letter = letter.lower()
    while letter in guessed_letters:
        letter = input("Dwse ena gramma pou den echei epilechthei: ")
    if letter == "ς":  # "ς" at the end of the word is same as "σ"
        guessed_letters.append("ς")
        letter = "σ"
    elif letter == "σ":
        guessed_letters.append("ς")

    while not letter.isalpha() or len(letter) != 1:
        if letter.isalpha() and len(letter) != 1:
            letter = input("Dwse ENA gramma: ")
            letter = letter.lower()
        elif letter.isdigit():
            letter = input("Dwse ena gramma kai ochi arithmo: ")
        elif not letter.isalpha() and not letter.isdigit():
            letter = input("Dwse ena gramma kai ochi symvola: ")
            letter = letter.lower()
            while letter in guessed_letters:
                letter = input("Dwse ena gramma pou den echei epilechthei: ")
        if letter == "ς":
            guessed_letters.append("ς")
            letter = "σ"
        elif letter == "σ":
            guessed_letters.append("ς")
    print(f"Gyros {rounds}: {letter}")
    while letter in guessed_letters:
        letter = input("Dwse ena gramma pοu den echei epilechthei: ")

    guessed_letters.append(letter)
    print(f"Fores emfanisis tou grammatos {letter}: {hidden_word.count(letter)}")
    if hidden_word.count(letter) == 0:  # with zero appearances of the letter is the wrong letter
        max_rounds += 1
        print(f"Lathi: {max_rounds}")

    for i in range(len(word)):  # convert the "_" with letter
        if word[i] in guessed_letters and find[i] == "_":
            find[i] = letter
            if find[len(find) - 1] == "σ":  # if the last letter is "ς" convert "σ" with "ς"
                find[len(find) - 1] = "ς"

    for i in range(len(find)):  # the progress of the word with letters and "_" both
        print(find[i], end="")
    print("")

    if find.count("_") == 0:  # if there is not any "_" in find then the word was found
        print("Vrikate tin leksi! ")
        break
    rounds += 1
    if max_rounds == 10:  # if wrongs reach the number of 10 player lose
        print(f"Chasate, i leksi itan: {hidden_word}")
        break

