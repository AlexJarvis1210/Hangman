import random
import os


def choose_word(category):
    """Choose a random word from the specified category's CSV file."""
    file_name = f"{category}.csv"

    # Read words from the CSV file
    try:
        with open(file_name, 'r') as file:
            words = [line.strip().lower() for line in file.readlines()]
    except FileNotFoundError:
        print(f"Error: {file_name} not found. Please ensure the file exists in the current directory.")
        exit()

    return random.choice(words)


def display_word(word, guessed_letters):
    """Generate the display string for the word with guessed letters revealed."""
    display = ''
    for letter in word:
        if letter in guessed_letters:
            display += letter
        elif letter == ' ':
            display += ' / '
        else:
            display += '_ '
    return display


def get_hint(word, guessed_letters):
    """Return a hint (unguessed letter) from the word."""
    for letter in word:
        if letter not in guessed_letters and letter != ' ':
            guessed_letters.add(letter)
            return letter
    return None


def get_initial_guesses(word_length):
    """Determine the initial number of guesses based on the word length."""
    if word_length <= 3:
        return 5
    elif word_length <= 6:
        return 6
    else:
        return 7


def play_hangman():
    """Play a game of Hangman with the given category."""
    # Choose a category
    while True:
        category = input("Choose a category (animals, fruits, or countries): ").lower()
        if category in ['animals', 'fruits', 'countries']:
            break
        else:
            print("Invalid category. Please choose from animals, fruits, or countries.")

    word = choose_word(category)
    guessed_letters = set()
    remaining_lives = get_initial_guesses(len(word))

    # Main game loop
    while True:
        print(display_word(word, guessed_letters))
        guess = input("Enter a letter, 'hint', or 'guess': ").lower()

        if guess == 'hint':
            # Check if the player has enough lives to use a hint
            if remaining_lives > 2:
                hint = get_hint(word, guessed_letters)
                if hint:
                    print("Hint: ", hint)
                    remaining_lives -= 2
                else:
                    print("No hints available.")
            else:
                print("You do not have enough lives to use a hint.")
        elif guess == 'guess':
            whole_word = input("Enter your guess for the whole word: ").lower()
            if whole_word == word:
                print("Congratulations! You've won the game!")
                break
            else:
                remaining_lives -= 1
                print("Incorrect guess. You have {} lives left.".format(remaining_lives))
        else:
            # Validate input
            if len(guess) != 1 or not guess.isalpha():
                print("Invalid input. Please enter a single letter, 'hint', or 'guess'.")
                continue

            # Process letter guess
            if guess in word:
                guessed_letters.add(guess)
                if set(word) - {' '} <= guessed_letters:
                    print("Congratulations! You've won the game!")
                    break
            else:
                remaining_lives -= 1
                print("Incorrect. You have {} lives left.".format(remaining_lives))

        if remaining_lives <= 0:
            print("You've run out of lives. The correct word was: ", word)
            break

while True:
    play_hangman()
    play_again = input("Would you like to play again? (yes or no): ").lower()
    if play_again != 'yes':
        break
