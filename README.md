# iebis_swdev_debugging
Source code to test debugging

## Instructions
First, Fork this project.

There are three exercises splitted in three branches of this repository. You must switch branches to checkout the code of each exercise.
Then, find the bugs that appear in each branch.
Fix the bugs if you can and answer to the questions proposed below.
Commit the code before checking out a different branch to avoid loosing the fixes that you have made to the code.

Once that you are done fixing bugs, to score you must:
1. Switch to the master branch.
2. Type below in this README.md file the answer to each question and paste some code that you have used to solve them.
3. Commit the changes
4. Push to your GitHub repository
5. Finally place a Pull Request so I can see your proposed answers

New Commit
## Exercises
### Exercise 1
When the object is created, WordAnalyzer has the class that holds different methods that analyzes characteristics of the word passed as argument when the object WordAnalyzer is created.
The methods on my laptop either return the correct value or don´t work

#### a) Why the method firstMultipleCharacter is returning "c" for the word comprehensive, when the correct answer should be "e"?

The firstMultipleCharacter method calls the find function which has two parameters: 
> a char and a position value. 
> The position value remains constant and doesn't moves forward, for that reason it stays at the first letter "c".  
    
#### b) Why the method firstRepeatedCharacter is throwing an exception?
The firstRepeatedCharacter gives a StringIndexOutOfBoundsException. This means it is attempting to fetch a value that is not there. The way to fix this is by reducing the word.length method by 1 to stay within the index.
 
#### c) Why the method countGroupsRepeatedCharacters returns 3 in one case when it should be 4?
The for loop initialises "i" at value = 1 which ignores the string character = 0 which could or could not have an identical character adjacent to it. 

However, once the initial value was set to 0 it would return another StringIndexOutOfBoundsException. To circumvent this problem an additional if statement was added to test if i is equal to 0 so that it may go on to the next letter.  

### Exercise 2
Here we are placing mines in a board game where we have several spaces. Since Space and Mine inherits from Element, the boards can contain this kind as well. We have 2 boards of different size and place a different number of mines on each one.

#### a) Why placing less bombs takes longer in the second case?
The RED_BOARD is a greater int than that of the BLUE_BOARD and the values are put using the Random class. Since of the constraint it is harder to randomly put the bombs in the BLUE_BOARD because there are almost the same mount of spaces there are.  
On the other hand the RED_BOARD takes less time because a smaller number of mines in proportion to the board size means that it is easier to randomly find a place where the mine is able to be kept. 

#### b) Knowing that usually there are going to be more bombs than spaces in the final boards, how would you change the method minningTheBoard to be more efficient?
I don't understand this question but it is easier to assign every space as a bomb

### Exercise 3
When the "d" reaches the value 1.0, the program should end, but it never does.

#### a) Why does not appear a message indicating that "d is 1"?
It has to do with the code not exiting the while loop. If we exit the while loop then the print function would print but because it is not there and there is no error message.

#### b) How will you fix it?
Decimals have a problem with java so I would just use int values.
