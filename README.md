# py-rock-paper-scissors
rock-paper-scissors game on pyton


import random 

Rock = 1
Paper = 2
Scissors = 3
Stop = 4

print("Welcome to Rock-Paper-Scissors!")
print("1) ✊ Rock")
print("2) ✋ Paper")
print("3) ✌️ Scissors")
print("4) ❌ Quit")

while True:
    try:
        player = int(input("Choose (1-4): "))
        if player == Stop:
            print("Thanks for playing! 👋")
            break
        if player not in [Rock, Paper, Scissors]:
            print("Invalid choice, try again.")
            continue
    except ValueError:
        print("Please enter a number (1-4).")
        continue

    computer = random.randint(1, 3)
    
    choices = {1: "✊ Rock", 2: "✋ Paper", 3: "✌️ Scissors"}
    print(f"Computer chose: {choices[computer]}")

    if player == computer:
        print("It is a tie!")
    elif (player == Rock and computer == Scissors) or \
         (player == Paper and computer == Rock) or \
         (player == Scissors and computer == Paper):
        print("You won 🎉")
    else:
        print("You lose 😢")
