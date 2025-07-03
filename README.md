# PrologProject
What is the problem?

We will be implementing a project based on the game of Chess using Prolog. This game will be testing the use of real time user inputs and since prolog is a declarative programming language we will the limitation of Prolog. In Prolog things can only be true or false and are based on rules. We will test the ability of prolog to apply strict rules, real time user inputs, and mimic state change in chess board.

- Two player

- User Inputs

- Read Inputs

- Board State Change

What is the something extra?
We implemented rule enforcement for the chess pieces. We also added a emoji print at the end when either side wins and when we 'quit' the game. We also numbered the board from 1-8 to represent the Y coordinates and a-h to represent the X coordinates. Another extra thing we did was including the ability for the player to quit the game by input.

1. Quit Game

2. write Emoji 0(^-^)0 when game ends {^.^}o[~] when quitting

3. Movement enforcement Rules / Boundaries

4. Included display for the Instructions/ Rules of the Game

Ex. Moving a pawn piece from a2 to a4, in coordinates X=1 Y=2 and X2=1 Y2=4

Unless a friendly piece is in it's way:

King  : one square in any direction (horizontally, vertically, or diagonally)

Queen : Up, Down, Right, Left, Diagonal both directions (multiple steps based on the boundaries of the Board)

Bishop : Diagonal both directions + backward diagonal movement (multiple steps based on the boundaries of the Board)

Rook  : Up, Down, Left, Right (multiple steps based on the boundaries of the Board)

Pawn  : Star first move: two square up or one square up, Rest of the Game: up one , Capture: Diagonal one (Can not move backwards)

Knight  : L-shape" movements - move two squares in any direction vertically followed by one square horizontally, or two squares in any direction horizontally followed by one square vertically

What did we learn from doing this?
(This should be written after you have done the work.)What is the bottom-line? Is functional programming suitable for (part-of) the task? Make sure you include the evidence for your claims.

Prolog was very suitable to implement rules for the Game of Chess. Since we did not have to include any False "True" values, we were able to just implement the rules that were true. We found that Prolog is well-suited for tasks that are based on rule-based logics like a Game of Chess. Chess has strict rules and boundaries making is suitable for Chess. We learned that it was difficult to change the state of the board given that Prolog was made so that the atoms were immutable. We found a way around it by storing the pieces in the chess into a list, and using recursive function to replace the piece on the Chess Board with a new piece, thus changing the state of the board. In object oriented programming it is easier since values are mutable. It was also difficult because prolog are rule base true function. To do any arithmetic calculation we needed to make a rule for it for it to be true. We can not simply type X=1, X2 = X+1, and expect it to return 2, prolog would return X2 = X+1, and X=1. We need to use make an atom with the rule as add(X,X1):- X1 is X+1. for the value to return the correct arithmetic calculation. Furthermore, Prolog is very strict when seeing if a value exits in the atom's body "a" and 'a' are both strings, but if we were to type member('a',["a"]) it would return false. The predicate returns false because prolog is a declarative programming language. It has to exactly match to return true because prolog is based on logic.

Prolog was also easier to code the Game of Chess in comparison to other languages because we did not have to implement loops or include check for false positive cases.


# PrologProject

A text-based Chess game implemented in Prolog, featuring full board initialization, player input handling, piece movement validation, and turn-based gameplay.

## Features

Standard 8x8 chessboard with all pieces initialized.

Validates legal moves for all chess pieces (pawn, knight, bishop, rook, queen, king).

Supports piece capturing and move restrictions based on chess rules.

Simple command-line interface for inputting moves in algebraic notation.

Alternating turns between White and Black players.

Detects game-ending conditions when a king is captured.

Graceful quit option during gameplay.

## Getting Started
Prerequisites

SWI-Prolog (recommended) or any Prolog interpreter.

## Installation
Clone the repository or download the source files:

git clone https://github.com/yourusername/prolog-chess.git

cd prolog-chess

### How to Play
Open your Prolog interpreter.

Load the game files:

?- [moves].
?- [test].
?- [instructions].
?- [piece_helper].  % or whatever your main file is named

#### Start the game:
?- start.

#### How to Play
Enter your moves in the format: a2a4.
This moves the piece from column a, row 2 to column a, row 4.

To quit the game, enter: quit.

#### Movement Rules
Pawn: Moves forward one square; two squares on first move; captures diagonally

Knight: Moves in an "L" shape; can jump over pieces

Bishop: Moves diagonally any number of squares, path must be clear

Rook: Moves vertically or horizontally any number of squares, path must be clear

Queen: Combines rook and bishop moves

King: Moves one square in any direction

Moves are validated against these rules and the current board state.

#### Code Overview
moves.pl: Main game loop, input parsing, board display, and game state updates

piece_helper.pl: Movement validation predicates for each piece type

instructions.pl: Displays instructions to the player

test.pl: Test predicates for development and debugging



