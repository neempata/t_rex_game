# T-Rex Runner Game

A simple endless runner game built with Python and Pygame. The player controls a T-Rex that must jump over randomly generated obstacles while the game gradually becomes faster and more challenging.

This project recreates the basic gameplay of the classic browser dinosaur game while using a custom purple, pink, and black color theme. It focuses on game loops, object-oriented programming, collision detection, gravity, keyboard controls, and real-time movement.

## Project Overview

The goal of the game is to keep the T-Rex alive for as long as possible. Obstacles move from the right side of the screen toward the player, and the T-Rex must jump over them before they collide.

The game keeps track of survival time instead of using a traditional point system. As time passes, the obstacle speed slowly increases, making each run more difficult than the last.

When a collision occurs, the game ends and the player can press the spacebar to immediately restart.

## Features

- Endless side-scrolling gameplay
- Spacebar-controlled jumping
- Gravity-based jump movement
- Random obstacle heights and spacing
- Gradually increasing game speed
- Rectangle-based collision detection
- Survival timer displayed on screen
- Instant restart after game over
- Custom purple, light pink, and black color palette
- Object-oriented structure using separate T-Rex and obstacle classes
- Smooth gameplay running at 60 frames per second

## Technologies Used

- Python
- Pygame
- Python `random` module
- Object-oriented programming

## How the Game Works

### 1. Game Window

Pygame creates an `800 × 200` game window. A horizontal line near the bottom of the screen represents the ground.

The game uses three main colors:

- Black for the background
- Purple for the T-Rex
- Light pink for the ground, obstacles, timer, and game-over message

### 2. T-Rex Movement

The T-Rex stays near the left side of the screen while the obstacles move toward it.

When the player presses the spacebar, a negative vertical velocity moves the T-Rex upward. Gravity is added during every frame, gradually pulling it back toward the ground.

The T-Rex can only jump while it is standing on the ground. This prevents the player from jumping repeatedly in midair.

### 3. Obstacle Generation

Obstacles are created on the right side of the screen with randomized heights. Their spacing is also randomized so that each run feels slightly different.

Every obstacle moves from right to left. Once an obstacle leaves the screen, it is removed from the obstacle list.

### 4. Increasing Difficulty

The game starts at a manageable speed. During every frame, the speed increases by a small amount.

This creates a gradual difficulty curve: the longer the player survives, the faster the obstacles approach.

### 5. Collision Detection

Both the T-Rex and the obstacles are represented by Pygame rectangles. The game checks whether the T-Rex rectangle overlaps any obstacle rectangle.

If an overlap is detected, the game enters its game-over state and stops updating the movement.

### 6. Timer and Restart

The timer records how many seconds the player survives and displays the result in the upper-left corner of the window.

After a collision, the screen displays:

```text
Game Over! Press SPACE to Restart
```

Pressing the spacebar resets the T-Rex, obstacles, speed, and timer so a new run can begin without closing the game.

## Controls

| Key | Action |
| --- | --- |
| `Space` | Jump |
| `Space` after game over | Restart the game |
| Close window | Quit the game |

## Requirements

- Python 3.x
- Pygame

## Installation

Clone or download the project, then open a terminal inside the project folder.

Install Pygame:

```powershell
python -m pip install pygame
```

## Running the Game

Run the Python file:

```powershell
python t_rex.py
```

The game window will open immediately. Press the spacebar to jump over the incoming obstacles.

## Project Structure

```text
for-github/
├── t_rex.py     Main game file
├── README.md    Project documentation
└── .gitignore   Files and folders excluded from Git
```

## Game Loop

The main game loop follows this process:

```text
Start Game
    |
    v
Read Keyboard and Window Events
    |
    v
Update Timer and Game Speed
    |
    v
Apply Jumping and Gravity
    |
    v
Generate and Move Obstacles
    |
    v
Check for Collisions
    |
    v
Draw the Game
    |
    v
Repeat at 60 FPS
```

## What I Learned

This project strengthened my understanding of how real-time games are structured around a continuous game loop. Instead of waiting for a user to enter a command, the program constantly reads events, updates positions, checks for collisions, and redraws the screen.

I learned how velocity and gravity can be used together to create a natural jumping effect. Giving the T-Rex an upward velocity begins the jump, while adding gravity during every frame brings it back down. The ground check also showed me how to stop an object at a fixed boundary and prevent double jumping.

Creating separate `TRex` and `Obstacle` classes helped me understand how object-oriented programming can keep game code organized. Each object manages its own position, movement, appearance, and state while the main loop controls how everything works together.

I also gained more experience with rectangle collision detection, random obstacle generation, frame-rate control, and game-state management. Resetting the game after a collision showed me how multiple variables and objects must return to their starting values at the same time.

Finally, this project demonstrated how small changes can shape the player experience. Random obstacle sizes make each run less predictable, and gradually increasing the speed creates difficulty without needing multiple levels.

## Future Improvements

Some improvements I would like to explore include:

- Replace the rectangles with animated T-Rex and cactus sprites
- Add a high-score system
- Save the best survival time between sessions
- Add sound effects for jumping, scoring, and collisions
- Include clouds, stars, or moving background layers
- Add a start screen and pause option
- Introduce different obstacle types
- Allow the T-Rex to duck under flying obstacles
- Improve obstacle spacing at higher speeds
- Add difficulty modes
- Display a score based on distance traveled
- Add pixel-style fonts and visual effects
- Package the game as a standalone executable

## Possible Challenges

### Pygame is not installed

If the program displays `ModuleNotFoundError: No module named 'pygame'`, install the dependency:

```powershell
python -m pip install pygame
```

### The game closes immediately

Run the project from a terminal so any error message remains visible:

```powershell
python t_rex.py
```

### The T-Rex does not jump

Click the game window to make sure it has keyboard focus, then press the spacebar.

## License

This project is open source and available for learning, practice, and modification.
