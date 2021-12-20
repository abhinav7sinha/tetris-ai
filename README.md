#####  <div align="center"> Tetris AI!

<br>

***
### [The Game of Quintris!]

***
#### Problem Statement:
The game of Quintris will likely seem familiar. It starts off with a blank board. One by one, random pieces
(each consisting of 5 blocks arranged in different shapes) fall from the top of the board to the bottom. As
each piece falls, the player can change the shape by rotating it or flipping it horizontally, and can change its
position by moving it left or right. It stops whenever it hits the ground or another fallen piece. If the piece
completes an entire row, the row disappears and the player receives a point. The goal is for the player to
score as many points before the board  fills up.

#### Inputs:

The program generates a string of moves ('mnbh') that correspond to right, rotate, left, horizontal flip movements
of the current piece in the game

#### Expected Output:

Corresponding to each move, the game prints the current board state on the screen.

#### Command:

<code> python3 ./quintris.py computer simple </code>

***

### Info:
- The program is designed to find the a combination of moves for which the cost function "def cost(self, quintris, quintris2)" is minimum.
- State Space: The state space is the set of all possible combinations of moves that can be made without the piece colliding with another piece on the board, or the edge of the board itself.
- Successor Function: To find all possible states, We calculate all the possible moves corresponding to each piece. For example, each piece can be moved horizontally from one edge of the board to another, also, they can be flipped horizontally two times, and rotated 4 times.
- Cost funtion: We assign weights to the following components based on hit and trial while testing:
  a. number of holes in the board
  b. difference between the maximum and minimum height of tiles
  c. difference in heights of adjacent tiles
  d. depth of wells in the board: empty spaces surrounded by tiles
  e. line clears
- Goal state: The goal state is a state with minimum cost -> this would ideally lead to a high score on the game over time
- Search algorithm: We use Expectimax algorithm to find the best move. We use a chance node to calculate the expected cost of a subsequent piece and add it to the cost for the next_piece and the cost for the current_piece.

### References:
1. https://inst.eecs.berkeley.edu/~cs188/fa18/assets/slides/lec7/FA18_cs188_lecture7_expectimax_search_and_utilities_1pp.pdf

***
