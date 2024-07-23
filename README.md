### README.md for GitHub Repository

```markdown
# 100 Days of Code with Python: Week 1 Recap

This repository contains the projects I worked on during the first week of my 100 Days of Code challenge with Python. Each project helped me enhance my Python skills and gain a deeper understanding of various concepts.

## Projects Overview

### Day 1: Cyber Guard Name Generator

**Project:** Cyber Guard Name Generator

**Summary:** A simple Python script that generates strong and secure-sounding names for cybersecurity firms.

**Key Learnings:**
- Using the `random` module to generate random names.
- Defining and calling functions.
- Using loops to iterate through lists.

**Code:**

```python
import random

adjectives = ["Secure", "Trusted", "Defender", "Guardian"]
nouns = ["Shield", "Protector", "Fortress", "Sentinel"]

def generate_name():
    adj = random.choice(adjectives)
    noun = random.choice(nouns)
    return f"{adj} {noun}"

print(generate_name())
```

### Day 2: Tip Calculator

**Project:** Tip Calculator

**Summary:** A simple tip calculator that helps users calculate the tip and total bill amount.

**Key Learnings:**
- Handling user input with the `input()` function.
- Converting strings to integers and floats.
- Performing arithmetic operations.

**Code:**

```python
print("Welcome to the best tip calculator!")
bill = float(input("What was the total bill? $"))
tip = int(input("How much tip would you like to give? 15, 20, or 25? "))
people = int(input("How many people to split the bill?"))

tip_as_percent = tip / 100
total_tip_amount = bill * tip_as_percent
total_bill = bill + total_tip_amount
bill_per_person = total_bill / people
final_amount = round(bill_per_person, 2)

print(f"Each person should pay: ${final_amount}")
```

### Day 3: Cyber-Security-Breach Maze Game

**Project:** Cyber-Security-Breach Maze Game

**Summary:** A maze game that simulates navigating through a cybersecurity breach.

**Key Learnings:**
- Working with nested lists.
- Using loops to navigate through a grid.
- Implementing game logic.

**Code:**

```python
maze = [
    ["#", "#", "#", "#", "#"],
    ["#", " ", " ", " ", "#"],
    ["#", " ", "#", " ", "#"],
    ["#", " ", "#", " ", "#"],
    ["#", "#", "#", "#", "#"]
]

def display_maze():
    for row in maze:
        print("".join(row))

display_maze()
```

### Day 4: Rock, Paper, Scissors Game

**Project:** Rock, Paper, Scissors Game

**Summary:** A classic Rock, Paper, Scissors game to practice conditional statements.

**Key Learnings:**
- Using conditional statements to control the game flow.
- Comparing user input with computer-generated choices.
- Implementing basic game logic.

**Code:**

```python
import random

choices = ["rock", "paper", "scissors"]
user_choice = input("Choose your weapon! Type rock, paper, or scissors: ").lower()
computer_choice = random.choice(choices)

print(f"Computer chose: {computer_choice}")

if user_choice == computer_choice:
    print("It's a draw.")
elif (user_choice == "rock" and computer_choice == "scissors") or \
     (user_choice == "paper" and computer_choice == "rock") or \
     (user_choice == "scissors" and computer_choice == "paper"):
    print("You win!")
else:
    print("You lose.")
```

### Day 5: Password Generator

**Project:** Password Generator

**Summary:** A password generator that creates strong and secure passwords.

**Key Learnings:**
- Creating lists of characters (letters, numbers, symbols).
- Using loops to select random characters.
- Combining characters to form a password.

**Code:**

```python
import random

letters = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'
numbers = '0123456789'
symbols = '!@#$%^&*()'

def generate_password(length):
    all_chars = letters + numbers + symbols
    password = ''.join(random.choice(all_chars) for _ in range(length))
    return password

print(generate_password(12))
```

### Day 6: Solving Reeborg's World Game Puzzles

**Project:** Reeborg's World Game Puzzles

**Summary:** Solving various puzzles in Reeborg's World to practice loops and conditional statements.

**Key Learnings:**
- Using loops to navigate through obstacles.
- Implementing functions to control robot actions.
- Solving puzzles using logical thinking.

**Code:**

```python
def turn_right():
    turn_left()
    turn_left()
    turn_left()

while not at_goal():
    if right_is_clear():
        turn_right()
        move()
    elif front_is_clear():
        move()
    else:
        turn_left()
```

### Day 7: Cybersecurity Hangman Game

**Project:** Cybersecurity Hangman Game

**Summary:** A fun and educational Hangman game focused on cybersecurity terms.

**Key Learnings:**
- Using lists to manage the game state.
- Implementing game logic with loops and conditionals.
- Enhancing the user experience with ASCII art.

**Code:**

```python
import random
from hangman_words import word_list
from hangman_art import logo, stages

print(logo)

chosen_word = random.choice(word_list)
word_length = len(chosen_word)
display = ["_"] * word_length
end_of_game = False
lives = 6

while not end_of_game:
    guess = input("Guess a letter: ").lower()
    if guess in display:
        print(f"You've already guessed {guess}")
    else:
        for position in range(word_length):
            if chosen_word[position] == guess:
                display[position] = guess
        if guess not in chosen_word:
            lives -= 1
            if lives == 0:
                end_of_game = True
                print("You lose.")
    print(" ".join(display))
    if "_" not in display:
        end_of_game = True
        print("You win.")
    print(stages[lives])
```
