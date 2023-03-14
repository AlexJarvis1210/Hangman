# Hangman
A version of the classic game Hangman. Part of the 30 day challenge by Matthew James Sevey

---------------------------------------------------------------------------------------------------------

Taken from Wikipedia(1)

History
Though the origins of the game are unknown, a variant is mentioned in a book of children's games assembled by Alice Gomme in 1894 called Birds, Beasts, and Fishes. This version lacks the image of a hanged man, instead relying on keeping score as to the number of attempts it took each player to fill in the blanks.

A version which incorporated hanging imagery was described in a 1902 Philadelphia Inquirer article, which stated that it was popular at "White Cap" parties hosted by "Vigilance Committees" where guests would wear "white peaked caps with masks"

Overview
The word to guess is represented by a row of dashes representing each letter of the word. Rules may permit or forbid proper nouns, such as names, places, brands, or slang. If the guessing player suggests a letter which occurs in the word, the other player writes it in all its correct positions. If the suggested letter does not occur in the word, the other player removes (or alternatively, adds) one element of a hanged stick figure as a tally mark. Generally, the game ends once the word is guessed, or if the stick figure is complete — signifying that all guesses have been used.

The player guessing the word may, at any time, attempt to guess the whole word.[3] If the word is correct, the game is over and the guesser wins. Otherwise, the other player may choose to penalize the guesser by adding an element to the diagram. On the other hand, if the guesser makes enough incorrect guesses to allow the other player to complete the diagram, the guesser loses. However, the guesser can also win by guessing all the letters that appear in the word, thereby completing the word, before the diagram is completed.

----------------------------------------------------------------------------------------------------------

I intened to make a variation of the original game to suit the Python terminal window and to add some extra interactivity for the player. Changes include:

- The player will choose a catagory from which the word will be chosen. For example, TV shows, Sports star, Movie titles, Famous Phrases.
- The player will get _n_ number of incorrect guesses before the answer is revealed (This will replace the old-style Hanging man drawing to suit Codespace's terminal window)
- The player gets 1 hint per round, if requsted.

----------------------------------------------------------------------------------------------------------

The program will select a random word (or words) from one of several predetermined lists (chosen by the user at the start) and reveal to the player how many letters there are in the secret word. For example, "The Hangman Game" would appear ___ / _______ / ____ , where each letter is replaced with a "_" _and a space replaced with a "/"

The player is then prmopted for a letter.
If the letter appears in the word then the program will show he player where abouts For example, the player chooses "A"
The game returns
___ / _a___a_ / _a__


If the player guesses a letter incorrectly the game will return:
Inccorect, you have n guesses left!

If the player runs out of guesses the game will show the correct answer.

At any time, the player can type "hint" and he game will provide at least 1 letter in the answer at the cost of 2 lives.

The player can guess the entire word by entering a keyword "guess"
If the player guesses correctly they have won the game.
If they guess incorrectly, they lose a life.

At the end of the game the player is asked if they would like to play again?
If yes, the process repeats.
If no, the program ends.

References

(1) Wikipedia (2023) _Hangman_(game)_.Available at: https://en.wikipedia.org/wiki/Hangman_(game) (Accessed 14th March 2023)
