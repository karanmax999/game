# Snake, Water, Gun Game

This is a simple Python implementation of the classic "Snake, Water, Gun" game. The game allows the user to play against the computer. The rules are simple:

- Snake (s) drinks Water (w): Snake wins
- Water (w) douses Gun (g): Water wins
- Gun (g) kills Snake (s): Gun wins

If both the user and the computer choose the same object, the game is a draw.

## How to Play

1. Clone this repository to your local machine.
2. Ensure you have Python installed.
3. Run the `main.py` script.
4. When prompted, enter your choice:
   - `s` for Snake
   - `w` for Water
   - `g` for Gun

The computer will randomly choose its option, and the winner will be determined based on the rules mentioned above.

## Code Explanation

```python
import random

'''
1 for snake
-1 for water 
0 for gun
'''

# Computer randomly chooses one of the options
computer = random.choice([-1, 0, 1])

# User inputs their choice
youstr = input("Enter your choice (s for snake, w for water, g for gun): ")
youDict = {"s": 1, "w": -1, "g": 0}
reverseDict = {1: "Snake", -1: "Water", 0: "Gun"}

# Check if user input is valid
if youstr in youDict:
    you = youDict[youstr]

    print(f"You chose {reverseDict[you]}\nComputer chose {reverseDict[computer]}")

    if computer == you:
        print("It's a draw")
    else:
        if computer == -1 and you == 1:
            print("You win!")
        elif computer == -1 and you == 0:
            print("You lose!")
        elif computer == 1 and you == -1:
            print("You lose!")
        elif computer == 1 and you == 0:
            print("You win!")
        elif computer == 0 and you == -1:
            print("You win!")
        elif computer == 0 and you == 1:
            print("You lose!")
        else:
            print("Something went wrong!")
else:
    print(f"Invalid choice: {youstr}. Please choose 's' for snake, 'w' for water, or 'g' for gun.")
```

The game logic checks if the user input is valid, and then compares the user's choice with the computer's choice to determine the winner. If the input is invalid, the game prompts the user to enter a valid choice.

## Future Improvements

- Add graphical user interface (GUI) for better user interaction.
- Include a scoreboard to keep track of wins, losses, and draws.
- Allow multiple rounds in a single game session.
