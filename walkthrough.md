Let's build 'Guess the Number'
==============================

Open a new file editor window by clicking on the File ► New Window. In the blank window that appears, type in the source code and save it as *guess.py*. 

(Then run the program by pressing F5. When you enter this code into the file editor, be sure to pay attention to the spacing at the front of some of the lines. Some lines have four or eight spaces of indentation.)

Work through this in your pair, typing out the code exactly as it appears here. (No copy and pasting - that's cheating!) Remember to get the spacing and syntax exact, computers aren't as forgiving as your history teacher! If there is something that you don't understand - ask your pair to explain it to you, that's part of the reason why it's so useful having a pair. Don't be afraid to ask Hannah or Google any questions you have.  

```
# this is a guess the number game
import random
```

The first line here is a *comment* - meaning Python will ignore everything after the # sign. This tells us and anyone else who might be reading our code what this programme does.

The second line is an *import statement*. While Python includes many built-in functions, some functions are packaged into separate **modules**. You can use these functions by importing their modules into your program with an import statement.

In our 'Guess the Number' game, Line 2 imports the module named random so that the program can call random.randint(). This function will come up with a random number for the user to guess.

```
guessesTaken = 0
```

Line 4 creates a new *variable* named guessesTaken. Since the player hasn’t made any guesses at this point in the programme, let's set it's initial value to 0. Explain to your pair why we need this variable in the programme. 

```
print("Hello! What is your name?")
myName = input()
```

These lines should be familiar! 
Line 6 is a function call to the print() function. Remember that a function is like a mini-programme inside your programme. When your programme calls a function, it runs this mini-programme. The code inside the print() function displays the *string* argument you passed it between the brackets.

Line 7 lets the user type in their name and stores it in the myName variable. (Remember, the string might not really be the player’s name. It’s just whatever string the player typed. Computers are dumb and just follow their instructions no matter what.)

```
number = random.randint(1, 20)
```

Line 9 calls a new function named randint() and stores the return value in the *variable* number. The randint() function is provided by the random module, so you must precede it with random. (Don’t forget the full-stop! This tells Python that the randint() function is in the random module).

####What does the randint() function do?####

The randint() function will return a random integer between (and including) the two integer arguments you pass to it. Line 9 passes 1 and 20 between the brackets separated by commas that follow the function name. The random integer that randint() returns is stored in a variable named number; this is the secret number the player is trying to guess.

Try different ranges of numbers by changing the arguments. For example, try random.randint(1000, 2000) to get integers between 1000 and 2000. Here's a good place to have a play with it in the interactive shell! 


