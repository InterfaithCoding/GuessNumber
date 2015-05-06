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

