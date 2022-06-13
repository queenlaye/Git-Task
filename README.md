# A Rock-Paper-Scissors game, Task

from random import choice


print("Welcome To Rock-Paper-Scissors Game")
print("***********************************")
print("CPU vs Player")


def user_option():
    player_choice = input("Please pick an option between R, P or S: ").upper()
    if player_choice == "R":
        player_choice = "R"
        
    elif player_choice == "P":
        player_choice = "P"
        
    elif player_choice == "S":
        player_choice = "S"
        
    else:
        print("Option not valid")
        user_option()

    return player_choice


available_options = ["R","P","S"]
computer_choice = choice(available_options)
    
player_choice = user_option()
choice_state = False

while choice_state == False:
    player_win = 0
    computer_win = 0

    if player_choice == "R":
        choice_state = True
        if computer_choice == "R":
            print("Player (Rock) : CPU (Rock), there is a tire")
            player_win = player_win
            computer_win = computer_win

        #  Rock beats scissors
        elif computer_choice == "S":
            print("Player (Rock) : CPU (Scissors), You Win")
            player_win += 1
            computer_win = computer_win

        # Paper beats Rock
        elif computer_choice == "P":
            print("Player (Rock) : CPU (Paper), Computer Win")
            computer_win += 1
            player_win = player_win

    elif player_choice == "P":
        choice_state = True
        if computer_choice == "P":
            print("Player (Paper) : CPU (Paper), there is a tire")
            player_win = player_win
            computer_win = computer_win

        # Paper beats Rock
        elif computer_choice == "R":
            print("Player (Paper) : CPU (Rock), You Win")
            player_win += 1
            computer_win = computer_win
    
        elif computer_choice == "S":
            print("Player (Paper) : CPU (Scissors), Computer Win")
            computer_win +=1 
            player_win = player_win

    elif player_choice == "S":
        choice_state = True
        if computer_choice == "S":
            print("Player (Scissors) : CPU (Scissors), there is a tire")
            player_win = player_win
            computer_win = computer_win
        
        elif computer_choice == "R":
            print("Player (Scissors) : CPU (Rock), Computer Win")
            computer_win += 1
            player_win = player_win

        # Scissors beats Paper
        elif computer_choice == "P":
            print("Player (Scissors) : CPU (Paper), You Win")
            player_win += 1
            computer_win = computer_win

    else:
        print("Invalid option selected, kindly select a valid option.")

else:
    choice_state

print("Player Wins: ",player_win)
print("CPU Wins: ",computer_win)
