# dsa.project
word scramble game

import random

# List of words and their hints
word_hints = {
    'python': 'A popular programming language 🐍',
    'computer': 'An electronic device you are probably using right now 💻',
    'science': 'Subject that explains natural phenomena 🔬',
    'programming': 'The art of writing code 💡',
    'keyboard': 'You type with this ⌨️',
    'internet': 'Connects people and data across the world 🌐',
    'software': 'You install this to run applications 🧠'
}

# Function to scramble a word
def scramble(word):
    word_letters = list(word)
    random.shuffle(word_letters)
    return ''.join(word_letters)

# Game function
def word_scramble_game():
    print("🎯 Welcome to the Word Scramble Game with Hints!")
    target_score = 5
    score = 0

    while score < target_score:
        original_word = random.choice(list(word_hints.keys()))
        scrambled_word = scramble(original_word)
        hint = word_hints[original_word]

        print(f"\n🔀 Scrambled Word: {scrambled_word}")
        print(f"💡 Hint: {hint}")
        guess = input("💬 Your guess: ")

        if guess.lower() == original_word:
            score += 1
            print(f"✅ Correct! Your score is now {score}/{target_score}.")
        else:
            print(f"❌ Wrong! The correct word was: {original_word}. Your score is {score}/{target_score}.")

    print("\n🏆 Congrats! You reached the target score with hints! 🎉")

# Start the game
word_scramble_game()
