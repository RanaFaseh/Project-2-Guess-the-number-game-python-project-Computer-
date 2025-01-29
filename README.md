import random

def guess_the_number():
    """Project 2: Guess the Number Game By (computer)"""
    random_number = random.randint(1, 100)
    guesses_left = 10
    print("Welcome to the Guess the Number Game!")
    print("I'm thinking of a number between 1 and 100.")
    print(f"You have {guesses_left} guesses left.")
    low = 1
    high = 100
    while guesses_left > 0:
        print(f"\nYou have {guesses_left} guesses left.")
        guess = (low + high) // 2  # Computer's guess (binary search)
        print(f"The computer guesses: {guess}")

        if guess < random_number:
            print("Too low! Try again.")
            low = guess + 1
        elif guess > random_number:
            print("Too high! Try again.")
            high = guess - 1
        else:
            print(f"Congratulation! The computer guessed the number in {10 - guesses_left + 1} tries.")
            return  # Exit the game loop if the guess is correct

        guesses_left -= 1

    print(f"\nThe computer ran out of guesses. The number was {random_number}.")

guess_the_number()
