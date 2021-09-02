# nQueens

This repository shows different algorithms to solve the [nQueens](https://en.wikipedia.org/wiki/Eight_queens_puzzle) problem.

## Description

The nQueen problem seeks to find ways to place n queens in a nxn chessboard so that no two queens threaten each other; thus, a solution requires that no two queens share the same row, column, or diagonal. There are different ways to approach this problem: this program compares the brute force and the fancy algorithm. To check the conditions for a queen to be safe, it uses the following methods iterated over all queens on the board.

```
def safeBoard(board):
   # Check all queens to be safe, return false if not safe
   
   for colQ1 in range(len(board)):
      for colQ2 in range(colQ1+1,len(board)):
         if checkVertical(board[colQ1], board[colQ2]) or checkDiagonal(board[colQ1], colQ1, board[colQ2], colQ2):
            return False
         
   return True

def checkVertical(rowQ1, rowQ2):
   # Return if two queens on horizontal
   return rowQ1 == rowQ2

def checkDiagonal(rowQ1, colQ1, rowQ2, colQ2):
   # return if two queens on diagonal
   diffRow = abs(rowQ1 - rowQ2)
   diffCol = abs(colQ1 - colQ2)
   
   return diffRow == diffCol
```

The chess board is imagined as a single dimensional array, where the value shows the rowth position for the queen in that column. The brute force method will have time complexity of O(N^N), so it will take enormous amounts of time to run boards larger than 9. For every position, this method checks the entire NxN board N number of times for N queens. So, if you increase n by one, the impact on runtime is very significant, since it also increases the size of the board. This happens because of the safeBoard[board] at the beginning of the method. This function checks if the board is safe for all positions, as it runs two loops that go through all columns, and verify that two queens are not standing in the same row, column, or diagonal. The loops are nested as such checkVertical and checkHorizontal are both called for N times (spanning the entire board). At the same time, the original function repeats for all positions, so since the safeBoard is called for the entire board for each position, the total complexity grows to N^N.

Instead, the nQueensFancy method will have complexity of O(N!), so reducing significantly runtime form the brute force method. This method starts with a queen at an edge, and makes sure to avoid possible attack position by checking with the method safeQueen. Unlike safeBoard - this method does not check the entire board, but only the values in the array up to the index of the current Queen. It uses both currentQueen (the index in the array - so the column in the board), and the value at such index (the row in the board), thus simplifying the two previous nested for loops. Then, the next queen is placed at a position only if deemed safe, so avoiding going through scenarios that are certainly not a solution. If the method goes through the entire board and cannot fit all queens, it backtracks and moves the position of the previous one. Generally, when we place a queen, it has N possible way to move, but when we place the next it will have N-1 possibilities, because it needs to avoid the row already occupied. Going forward, this gives N*(N-1)*(N-2)...(N-(N-1)), which is equal to complexity O(N!).



## Getting Started

The program runs using Python, and importing time library and functions from the tools.py file.

### Executing program

To change the number of queens to check, modify the following line, and adapt the showBoard conditions to display the solution.

```
def main():
   compare(["Fancy"],
      [lambda x : nQueensFancy(x, True)],
      [4,5,6,7,8,9])
```


## License

This project is licensed under The Unlicense - see the LICENSE.md file for details


## Version History

* 0.1
    * Initial Release



