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

In our 'Guess the Number' game, Line 2 imports the module named random so that the program can call random.randint(). This function will come up with a random number for the player to guess.

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

Line 7 lets the player type in their name and stores it in the myName variable. (Remember, the string might not really be the player’s name. It’s just whatever string the player typed. Computers are dumb and just follow their instructions no matter what.)

```
number = random.randint(1, 20)
```

Line 9 calls a new function named randint() and stores the return value in the *variable* number. The randint() function is provided by the random module, so you must precede it with random. (Don’t forget the full-stop! This tells Python that the randint() function is in the random module).

####What does the randint() function do?####

The randint() function will return a random integer between (and including) the two integer arguments you pass to it. Line 9 passes 1 and 20 between the brackets separated by commas that follow the function name. The random integer that randint() returns is stored in a variable named number; this is the secret number the player is trying to guess.

Try different ranges of numbers by changing the arguments. For example, try random.randint(1000, 2000) to get integers between 1000 and 2000. Here's a good place to have a play with it in the interactive shell! 

####Welcoming the Player###

```
print('Well, ' + myName + ', I am thinking of a number between 1 and 20.')
```

On line 10 the print() function welcomes the player by name, and tells them that the computer is thinking of a random number. The plus signs *concatenate* the three strings to evaluate down to one string.

####Loops####
```
while guessesTaken < 6:
  print('Take a guess.') # There are four spaces in front of print.
  guess = input()
  guess = int(guess)

  guessesTaken = guessesTaken + 1

  if guess < number:
    print('Your guess is too low.') # There are eight spaces in front of print.

  if guess > number:
    print('Your guess is too high.')

  if guess == number:
    break
```

Line 12 is a while statement, which indicates the beginning of a *while loop*. A while statement always has a : colon after the condition. 

Let's break down this while statement: the expression that follows the *while* keyword contains two values 
1. The value in the variable guessesTaken
2. the integer value 6

These values are connected by the "<" (less than) operator. Comparison operators compare two values and evaluate to a True or False Boolean value. If you don't remember what a Boolean value is - ask your pair or Google it!

If the condition evaluates to True (which it does the first time, because the value of guessesTaken is 0), we enter the while-block at line 13 and keep going down. Once the program reaches the end of the while-block, instead of going down to the next line, the computer loops back up to the while statement’s line (line 12) and re-evaluates the condition. As before, if the condition is True the execution enters the while-block again. Each time the execution goes through the loop is called an iteration.

**As long as the condition is True, the program keeps executing the code inside the while-block repeatedly until the first time the condition is False.** 

####The Player Guesses####

We're going to have a closer look at the code in the while-block. Remember your indentation! 

```
  print('Take a guess.') # There are four spaces in front of print.
  guess = input()
```

Lines 13 to 17 ask the player to guess what the secret number is and lets them enter their guess. That number is stored in a variable named guess.

```
  guess = int(guess)
```

The input() function always returns a *string* of text that the player typed. Later in the programme we want to compare if the guess is greater than, less than, or equal to the secret number in the number variable. If we want to compare two numbers we need them to be of the same data type - they should both be *integers*. Line 15 overwrites the string value in guess with the integer value returned by int() function. 

```
  guessesTaken = guessesTaken + 1
```

You might have been wondering how we can keep track of guesses taken by our player. We set its value to 0 at the beginning of the programme - but we want it to increase by 1 each time a guess is taken. Each time the code loops through the while-block, Python will take this value and add 1 to it. This new increased value is then stored as the value of guessesTaken. Think of this line as meaning: "the guessesTaken variable should be one more than what it already is". 

```
  if guess < number:
    print('Your guess is too low.') # There are eight spaces in front of print.
```

Line 19 is an *if statement*. The execution will run the code in the following block if the if statement’s condition evaluates to True. If the condition is False, then the code in the if-block is skipped. Using if statements, you can make the program only run certain code when you want it to.

Line 19 checks if the player’s guess is less than the computer’s secret number. If so, then the execution moves inside the if-block on line 20 and prints a message telling the player this.

Unlike *while statements*, *if statements* don’t loop. 

```
  if guess > number:
    print('Your guess is too high.')
```

Line 22 checks if the player’s guess is greater than the secret number. If this condition is True, then the print() function call tells the player that their guess is too high.

```
  if guess == number:
    break
```

The if statement on line 25 checks if the guess is equal to the secret number. If it is, the program runs the break statement on line 26.

A break statement tells the execution to jump immediately out of the while-block to the first line after the end of the while-block. The break statement doesn’t bother rechecking the while loop’s condition.

```
if guess == number:
  guessesTaken = str(guessesTaken)
  print('Good job, ' + myName + '! You guessed my number in ' + guessesTaken + ' guesses!')
```

Line 28 has no indentation, which means the while-block has ended and this is the first line after the while-block. The execution left the while-block either because the while statement’s condition was False (when the player runs out of guesses) or the break statement on line 26 was executed (when the player guesses the number correctly).

Line 28 checks to see if the player guessed correctly. If so, the execution enters the if-block at line 

Lines 29 and 30 only execute if the condition in the if statement on line 28 was True (that is, if the player correctly guessed the computer’s number).

Line 29 calls the str() function, which returns the string form of guessesTaken. Line 30 concatenates strings to tell the player they have won and how many guesses it took them. Only string values can concatenate to other strings. This is why line 29 had to change guessesTaken to the string form. Otherwise, trying to concatenate a string to an integer would cause Python to display an error.

```
if guess != number:
  number = str(number)
  print('Nope. The number I was thinking of was ' + number)
```

Line 32 uses the “not equal to” comparison operator != to check if player’s last guess is not equal to the secret number. If this condition evaluates to True, the execution moves into the if-block on line 33.

Lines 33 and 34 are inside the if-block, and only execute if the condition on line 32 was True.

In this block, the program tells the player what the secret number they failed to guess correctly was. This requires concatenating strings, but number stores an integer value. Line 33 will overwrite number with a string form so that it can be concatenated to the 'Nope. The number I was thinking of was ' string on line 34.

At this point, the execution has reached the end of the code, and the program terminates. Congratulations! You’ve just programmed your first real game!

