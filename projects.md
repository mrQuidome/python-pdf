# Simple Task Manager CLI App

## Overview

Build a command-line **task manager** that supports:

- Creating, editing, and completing tasks
- Organizing tasks by tags (using dictionaries)
- Saving and loading task lists (JSON or pickle)
- Logging user actions
- Full test suite using `pytest` or `unittest`

## Core Features

1. **Object-Oriented Design**
   - Class `Task`: represents a single task (title, deadline, tags, status)
   - Class `TaskManager`: holds tasks in a dict (`task_id` → `Task`)
   - Optional class `CLI` or just procedural CLI logic
2. **Use of `dict`**
   - Internal storage: `self.tasks: Dict[int, Task]`
   - Tags: `Dict[str, List[int]]` mapping tags to task IDs
3. **Testing with `pytest`**
   - Unit tests for `Task` behavior (e.g. mark as complete)
   - Unit tests for `TaskManager` (e.g. add, delete, find, tag filter)
4. **Logging**
   - Log every action (e.g. task created, completed, deleted)
   - Write logs to a file with timestamped entries
5. **Persistence (Bonus)**
   - Save/load tasks as JSON or pickle
   - Command to export/import from file
   - prioritize tasks

# Tic Tac Toe CLI

## Goal

Implement a command-line Tic Tac Toe game in Python with:

- A clear object-oriented design
- Automated unit tests
- Logging of moves and game results
- Use of dictionaries for game state or players

The program should support:

- Two human players alternating turns
- Game board display and user input
- Win/draw detection
- Logging of all moves and outcomes

## Requirements

### 1. **Object-Oriented Structure**

Implement at least the following classes:

- `Game`: main controller
- `Board`: tracks the 3×3 grid
- `Player`: represents a player (name, symbol)
- (Optional) `Move` or `Logger` class for logging actions

### 2. **Game State**

- Use a dictionary to represent the grid:

  ```
  python
  
  
  CopyEdit
  self.grid = {(0, 0): None, (0, 1): 'X', ...}
  ```

- Or a list of lists is allowed if well-encapsulated

### 3. **Input / Output**

- Simple CLI interaction:
  - Print board
  - Prompt player for moves (e.g., `Enter row,col:`)

### 4. **Validation**

- Reject invalid moves (occupied cells or out of bounds)
- Detect win or draw after every move

### 5. **Logging**

- Log each move with timestamp to `game.log`
- Log game start and result

### 6. **Testing**

- Create a test file (e.g. `test_game.py`) with:
  - Tests for win detection
  - Tests for draw detection
  - Tests for move validation
  - Use `pytest` or `unittest`

## Stretch Goals

- Add simple AI (`random`, `block-win`)
- Replay log file to reconstruct game
- Save/load game state to file

# Minesweeper CLI

## Goal

Implement a simplified **command-line Minesweeper game** in Python. The player reveals cells in a hidden grid, trying to avoid mines. The game should be structured using object-oriented principles, with testable components and logging.

## Core Features

### 1. **Object-Oriented Design**

Implement at least the following classes:

- `Game`: orchestrates the game loop
- `Board`: manages the grid, mine placement, and display
- `Cell`: represents an individual cell (state: revealed, flagged, mined, adjacent mine count)
- (Optional) `PlayerAction`, `Logger`, or `Config` classes

### 2. **Grid Representation**

Use a dictionary for the internal grid:

```python
self.cells = {(x, y): Cell(), ...}
```

Where `x` and `y` are coordinates on the board (e.g., 9×9 or 10×10).

or a list of lists

### 3. **Gameplay**

- Prompt the player for input like `reveal 3,5` or `flag 2,1`
- Reveal logic should support recursive uncovering of 0-adjacent-mine cells
- Display the board (concealed cells as `·`, flagged as `F`, revealed numbers)

### 4. **Rules & Win Conditions**

- Player loses by revealing a mine
- Player wins when all non-mine cells are revealed
- Flags are optional for solving but helpful

### 5. **Logging**

- Log all user actions (`reveal`, `flag`) with timestamps
- Log game start, victory, or defeat in `minesweeper.log`

### 6. **Testing**

Write a test file (e.g. `test_board.py`) with:

- Unit tests for mine placement
- Tests for adjacent mine counting
- Tests for reveal propagation
- Tests for win/loss detection
   Use `pytest` or `unittest`.

## Stretch Goals

- Add a simple timer and high score logging
- Support multiple board sizes
- Save/load game state to a file