# Sudoku
Sudoku solver using Backtracking
So I have created a sudoku game board solver using java .
What are the properties of a 9x9 sudoku ?
1.Every row should contain numbers 1-9 and no number can be repeated for that row
2.Every column should contain number 1-9 and no number can be repeated for that column
3.Starting from top left corner to bottom right corner, every 3x3 square should contain numbers 1-9 and no number can be repeated for that square

This code contains various user-built functions that will help me to solve a given unsolved board of sudoku.

The first function I have used is printBoard() that recieves the unsolved board as a 2D array.This function is just to display the board in the output screen.
I have used 2 for loops; 
  outer loop is used to print dotted lines for every 3 rows 
  inner loop is used to print vertical line for every 3 columns
 This will collectively arrange the sudoku in 3x3 squares 
 And just print the elements of 2D array
 
 The 2nd function is isNumberRow() which recieves the 2Darray, the number to be checked and row in which it will be checked.
 I used a for loop that iterates through the row and if board[row[i]] matches with number , we return true
 if for loop ends , we return false
 
 The 3rd function is isNumberColumn() which recieves the 2Darray, the number to be checked and column in which it will be checked.
 I used a for loop that iterates through the column and if board[column[i]] matches with number , we return true
 if for loop ends , we return false
 
 The 4th function is isNumberInBox() which recieves the 2Darray, the number to be checked and column and row in which it will be checked(the 3x3 square).
 For this, we take two integer variables, lets say a and b .
 we initialize a to (row - row%3) and b to (column - column%3), what this does is , lets say row is 5 and column is 7, this makes a =3 and b = 6 which means
 it will look for the 3x3 square starting from row =3 and column = 6
 So we use 2 for loops 
 Inner iterates from b to b+3 (because we need a 3x3 square) and outer iterates from a to a+3 .
 Then we simply check if number exists in that square and return true
  if outer for loop ends , we return false
  
  The 5th function is isValidPlacement() that receives the 2D array , the number, row and column
  This function will basically call all the above 3 function and return the negative of whatever every function returns.This is because every function 
  returns true if the number exists in them. This function returns true only if number is not in row ,not in column and not in square.
  
  The 6th function is solveBoard() that receives the 2d array and solves it
  i have used 3 for loops
 the first two so it iterates for every row and every column
 next we first check whether the space if empty or not, if its empty(contains 0) we call the next for loop that will add a number in range 1-9 to that empty space.
 we call isValidPlacemnt() inside the for loop that will check for every number from 1-9 and if it returns true , we place that number inside that space.
 
 Inside main we just create a sudoku board using the 2d array and simply calling function solveBoard() to this array will solve the sudoku board.
 
