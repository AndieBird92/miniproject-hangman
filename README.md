# Hangman (Python)

A classic terminal-based Hangman game built in Python and Jupyter Notebook. Guess the hidden fruit or vegetable one letter at a time before you run out of lives — complete with ASCII-art gallows that build up as you make mistakes.

## How to Play

1. Run the notebook cells in order (or the exported script) to start the game.
2. A random word is chosen from the word list, and its length is shown as a row of blanks (`_`).
3. Type one letter at a time when prompted.
   - If the letter is in the word, it's revealed in its correct position(s).
   - If not, you lose a life and the hangman drawing progresses one stage.
4. You start with **10 lives**.
5. Guess the whole word before your lives run out to win. Run out of lives, and the game reveals the word and ends.

## Features

- **Word bank** of 20 fruits and vegetables (e.g. Potato, Broccoli, Pomegranate, Cauliflower).
- **ASCII-art hangman** with 12 stages, from an empty gallows to a full win/lose screen.
- **Input validation** — rejects anything that isn't a single letter (a–z).
- **Duplicate guess detection** — won't penalize you for re-guessing a letter.
- **Live feedback** after every guess (correct, incorrect, or already guessed).
- **Guessed letters tracker**, displayed in sorted order each round.
- **Win/Lose end states**, each with their own ASCII banner, followed by an automatic game reset.

## Project Structure

The game logic is organized into a `game_state` dictionary that tracks:

| Key | Description |
|---|---|
| `GameOngoing` | Whether a round is currently active |
| `Solution` | The word to guess |
| `Lives` | Remaining lives (starts at 10) |
| `GuessedLetters` | List of letters guessed so far |
| `Display` | Current word display with blanks and revealed letters |
| `Feedback` | Message shown after the last guess |

Core functions:

- `start_game()` — initializes a new round with a random word and fresh state.
- `end_game()` — clears the game state after a round ends.
- `update_display()` — rebuilds the blank/revealed-letter display string.
- The **main game loop** — handles input, life deduction, win/lose checks, and rendering each round.

## Requirements

- Python 3
- Jupyter Notebook (to run the `.ipynb` file directly), or export to a `.py` script to run from the command line.

## Possible Improvements

- Add difficulty levels (shorter/longer words, fewer lives).
- Support custom word lists or categories.
- Track win/loss stats across multiple rounds.
- Convert to a `.py` script with a proper `if __name__ == "__main__":` entry point for easier CLI use.
