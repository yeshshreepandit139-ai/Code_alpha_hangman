import random

# Small list of predefined words
WORDS = ["python", "banana", "guitar", "planet", "window"]
MAX_WRONG = 6


def show_status(word, guessed, wrong_count):
    """Print the word with blanks, plus the current game state."""
    display = ""
    for letter in word:
        if letter in guessed:
            display += letter + " "
        else:
            display += "_ "
    print("\nWord:", display)
    print("Guessed letters:", " ".join(sorted(guessed)) if guessed else "none")
    print("Wrong guesses left:", MAX_WRONG - wrong_count)


def play():
    word = random.choice(WORDS)
    guessed = []
    wrong_count = 0

    print("=== HANGMAN ===")
    print("Guess the word one letter at a time. You get 6 wrong guesses.")

    while wrong_count < MAX_WRONG:
        show_status(word, guessed, wrong_count)

        # Check for a win
        won = True
        for letter in word:
            if letter not in guessed:
                won = False
        if won:
            print("\nCongratulations! You guessed the word:", word)
            return

        guess = input("Enter a letter: ").lower().strip()

        # Validate input
        if len(guess) != 1 or not guess.isalpha():
            print("Please enter a single letter.")
        elif guess in guessed:
            print("You already guessed that letter.")
        else:
            guessed.append(guess)
            if guess in word:
                print("Good guess!")
            else:
                wrong_count += 1
                print("Wrong guess!")

    print("\nGame over! The word was:", word)


# Main loop: allow replaying
while True:
    play()
    again = input("\nPlay again? (y/n): ").lower().strip()
    if again != "y":
        print("Thanks for playing!")
        break