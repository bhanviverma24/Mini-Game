# Mini-Game
#Taking user and computer score as 0.
uscore=0     
cscore=0       

#Creating loop
while True:
    
    #importing python libraries.
    import random     
    import sys
    from termcolor import colored,cprint
    
    pattern1=colored("*","green","on_green")
    print("*"*60)
    print(pattern1*60)
    print(pattern1*19,colored("Welcome To The Game!","green"),pattern1*19)
    print(pattern1*60)
    print("*"*60,"\n")
    print(colored("*"*20,"blue","on_blue"),colored("Enter Your Choice ","blue") ,colored("*"*20,"blue","on_blue"),"\n\n","Rock | Paper | Scissors","\n")
         
    #Getting User and Computer Choice.
    userin=input(colored("User Choice:","cyan",attrs=["dark","bold"]))       
    choices=["rock","paper","scissors"]    
    compin=random.choice(choices)   
    print((colored("Computer Choice:","magenta")),colored(compin,"magenta"))    
    
    #Comparing Choices.
    if userin.lower()==compin:
       print(colored("Tie","blue"))
        
    elif userin.lower()=="scissors":
        if compin=="rock":
            cscore+=1
            print(colored("You lose... Rock smashes Scissors","red"))
        else:
            uscore+=1
            print(colored("You Win! Scissors Cuts Paper ","blue"))
            
    elif userin.lower()=="rock":
        if compin=="paper":
            cscore+=1
            print(colored("You lose... Paper Covers Rock","red"))
           
        else:
            uscore+=1
            print(colored("You Win! Rock Smashes Scissors","blue"))
            
    elif userin.lower()=="paper":
        if compin=="scissors":
            cscore+=1
            print(colored("You lose... Scissors Cuts Paper","red"))
            
        else:
            uscore+=1
            print(colored("You Win! Paper Covers Rock","blue"))
    elif userin.lower() not in choices:
        print(colored("**Invalid  User Choice**","red"))
        
    #Getting User input, either to Continue the Game or Not.   
    cont=input("Continue the Game? (Y/N): ") 
         
    if cont.lower() != "y":
        print(colored("*"*23,"red","on_red"),colored("End the Game","red") ,colored("*"*23,"red","on_red"))
        print(("\nFinal Scores:\n"),colored("User:","cyan"),colored(uscore,"cyan"),"\n",colored("CPU:","magenta"),colored(cscore,"magenta") )
        print("*"*60)       
        break
        
