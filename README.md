import random

number = random.randint(1, 100)
guess = 0
tries = 0

print("Welcome to the Number Guessing Game!")
print("I'm thinking of a number between 1 and 100.")

while guess != number:
    try:
        guess = int(input("Take a guess: "))
        tries += 1
        if guess < number:
            print("Too low!")
        elif guess > number:
            print("Too high!")
    except ValueError:
        print("Invalid input. Please enter a number.")

print(f"Congratulations! You guessed the number in {tries} tries.")

import random

number = random.randint(1, 100)
max_tries = 7
tries = 0

print("Welcome to the Number Guessing Game!")
print("I'm thinking of a number between 1 and 100. You have 7 tries.")

while tries < max_tries:
    try:
        guess = int(input("Take a guess: "))
        tries += 1
        if guess == number:
            print(f"Congratulations! You guessed the number in {tries} tries.")
            break
        elif guess < number:
            print("Too low!")
        else:
            print("Too high!")
        print(f"You have {max_tries - tries} tries left.")
    except ValueError:
        print("Invalid input. Please enter a number.")
else:
    print(f"You ran out of tries. The number was {number}.")

import random

def play_game(difficulty):
    if difficulty == "easy":
        number = random.randint(1, 50)
        max_tries = 10
    elif difficulty == "medium":
        number = random.randint(1, 100)
        max_tries = 7
    elif difficulty == "hard":
        number = random.randint(1, 200)
        max_tries = 5
    else:
        return "Invalid difficulty level."

    tries = 0
    print(f"You chose {difficulty} difficulty. You have {max_tries} tries.")

    while tries < max_tries:
        try:
            guess = int(input("Take a guess: "))
            tries += 1
            if guess == number:
                print(f"Congratulations! You guessed the number in {tries} tries.")
                return
            elif guess < number:
                print("Too low!")
            else:
                print("Too high!")
            print(f"You have {max_tries - tries} tries left.")
        except ValueError:
            print("Invalid input. Please enter a number.")
    print(f"You ran out of tries. The number was {number}.")


difficulty = input("Choose difficulty (easy, medium, hard): ").lower()
result = play_game(difficulty)
if result:
    print(result)
