# Tic-tac-toe with minimax search

A small search-based AI prototype that picks the best move in tic-tac-toe. Built for Module 1 (Introduction to AI) of the AI Specialisation at Tokio School.

> The notebook is written in European Portuguese, as it was submitted for the course.

## What it does

Given a board and the player to move, the program chooses a move automatically using **minimax**:

- It simulates every possible move, the opponent's replies, and so on, until the game ends.
- Each final position is scored from the computer's point of view: +1 win, 0 draw, -1 loss.
- It assumes both players play perfectly: the computer takes the highest score and the opponent the lowest.
- It plays the square with the best score.

The function is recursive and works on a copy of the board, so the original is never changed. A counter records how many positions the search evaluates.

## Data

`tabuleiros_teste.csv` holds 10 hand-made test boards (description, board, player to move, expected move). The notebook creates this file and then checks the minimax move against the expected one for each board.

## Results (from the run submitted for the course)

- The minimax move matched the expected move on **10 out of 10** test boards.
- The number of positions evaluated grows fast: from 156 positions in one example to 549,945 on an empty board. Exhaustive search only works for small games like this one.
- A full game against the computer (human as X, computer as O) ended in a draw.

The notebook in this repository has no saved outputs. Run it to see the results.

## Limitations and possible improvements

- It does not learn and only works for this game.
- When several moves have the same score, it always takes the first one. It is predictable and does not always choose the quickest win (the notebook shows an example).
- Ten test boards are not enough to prove it is right in every position.
- Improvements: take search depth into account in the score, use alpha-beta pruning, pick randomly between equal moves, and test every possible board.

## How to run

Python 3 only, no extra libraries (it uses the standard `csv` module).

1. Open `tic_tac_toe_minimax.ipynb` in Jupyter or VS Code.
2. Run all cells. The "play against the computer" cell asks for your moves with `input()`.
