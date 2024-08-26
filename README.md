# number-guessing-game-



    import random
    def number_finding_game():
        print("Welcome to the Enhanced Number Finding Game!")
        
        while True:
            # Select difficulty level
            print("\nChoose a difficulty level:")
            print("1. Easy (1-50)")
            print("2. Medium (1-100)")
            print("3. Hard (1-200)")
            
            difficulty = input("Enter the number corresponding to your choice: ")
            
            if difficulty == '1':
                max_number = 50
            elif difficulty == '2':
                max_number = 100
            elif difficulty == '3':
                max_number = 200
            else:
                print("Invalid choice, please select a valid difficulty level.")
                continue
            
            # Generate a random number based on difficulty level
            number_to_guess = random.randint(1, max_number)
            
            # Set the number of attempts
            attempts = 0
            
            while True:
                # Ask the player to guess the number
                
                try:
                    guess = int(input(f"Enter your guess (1-{max_number}): "))
                    attempts += 1
                except ValueError:
                    print("Please enter a valid number.")
                    continue
                
                # Check if the guess is correct
                
                if guess < number_to_guess:
                    print("Too low! Try again.")
                elif guess > number_to_guess:
                    print("Too high! Try again.")
                else:
                    print(f"Congratulations! You found the number {number_to_guess} in {attempts} attempts.")
                    break
            
            # Ask the player if they want to play again
            
            play_again = input("Do you want to play again? (yes/no): ").lower()
            
            if play_again != 'yes':
                print("Thanks for playing! Goodbye!")
                break
    
    # Start the game
    
    number_finding_game()
