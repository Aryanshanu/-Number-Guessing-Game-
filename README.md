import random

def number_guessing_game():
    # Generate a random number between 1 and 100
    target_number = random.randint(1, 100)
    attempts = 0
    guessed_correctly = False

    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")

    # Loop until the player guesses the correct number
    while not guessed_correctly:
        # Take input from the player
        guess = input("Enter your guess (or type 'exit' to quit): ")

        # Allow the player to exit the game
        if guess.lower() == 'exit':
            print("Thanks for playing! Goodbye.")
            return

        # Validate input
        if not guess.isdigit():
            print("Please enter a valid number between 1 and 100.")
            continue
        
        guess = int(guess)

        # Check if the guess is within the valid range
        if guess < 1 or guess > 100:
            print("Your guess must be between 1 and 100. Try again.")
            continue

        attempts += 1  # Increment the attempt counter

        # Decision making to check the guess
        if guess < target_number:
            print("Too low! Try again.")
        elif guess > target_number:
            print("Too high! Try again.")
        else:
            guessed_correctly = True
            print(f"Congratulations! You've guessed the number {target_number} in {attempts} attempts.")

# Run the game
number_guessing_game()
