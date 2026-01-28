# Number-guessing-game-
Just a number guessing game 
mport random
from colorama import Fore, Style

secret_number = random.randint(1, 100)
print(Fore.CYAN + "I have picked a random number between 1 and 100" + Style.RESET_ALL)

try_1 = 0
max_tries = 3
while try_1 < 3:
    try:
    	guess = int(input(Fore.CYAN + "pick a number? " + Style.RESET_ALL))
    except ValueError:
    	print(Fore.YELLOW + "please input a number: " + Style.RESET_ALL)
    if guess < secret_number:
        print(Fore.RED + "Too low!" + Style.RESET_ALL)
        try_1 += 1
    elif guess > secret_number:
        print(Fore.RED + "Too high!" + Style.RESET_ALL)
        try_1 += 1
    else:
        print(Fore.GREEN + "correct" + Style.RESET_ALL)
        break
if try_1 == 3:
    print("sorry, the number was:", Fore.CYAN + str(secret_number))
