# Chess Bot 

This repository contains the source code for my chess bot, which was developed for the AI course at BITS Pilani. The bot was ranked second in the class tournament, where it competed against other AI bots in the arena hosted on GitHub at [SimpleChessArena](https://github.com/Aritra/SimpleChessArena).

## Features

- **Alpha-Beta Pruning:** The bot utilizes the alpha-beta pruning algorithm to optimize move selection by minimizing the number of nodes evaluated in the search tree.
- **Quiescence Search:** A quiescence search function is included to avoid the horizon effect and handle positions with potential tactical swings.
- **Piece-Square Tables:** The evaluation function uses piece-square tables to factor in positional strengths for pawns, knights, bishops, rooks, queens, and kings.
- **Material Evaluation:** The bot assigns scores based on material imbalances, where each piece type has a predefined value.
- **Transposition Table:** A transposition table is implemented to store previously evaluated board states, speeding up subsequent evaluations.
- **Adaptable for Black and White:** The bot is adaptable for both white and black, adjusting its evaluation logic accordingly.

## Code Structure

1. **Evaluation Charts:** Positional scoring tables for each piece type, such as pawns, knights, bishops, rooks, queens, and kings.
2. **Transposition Table Class:** A class to store board states and their evaluations, improving efficiency in searching.
3. **`group1` Class:** This class contains the core AI logic, including board evaluation, move selection using alpha-beta pruning, and quiescence search.
   - `evaluate_board(board)`: Evaluates the current board state using a combination of material and positional considerations.
   - `select_move(board)`: Selects the best move by exploring all legal moves with alpha-beta pruning and quiescence search.
   - `alphabeta(alpha, beta, depthleft, board)`: Performs the alpha-beta pruning.
   - `quiesce(alpha, beta, board)`: Ensures accurate evaluation in positions where captures are likely.
   - `makemove(board)`: Returns the selected move in UCI format.

## How to Use

1. **Install Dependencies:**
   Make sure you have `python-chess` installed:
   ```bash
   pip install chess
