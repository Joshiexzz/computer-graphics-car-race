# Computer Graphics Car Race Game

A 2-player car racing game developed using **Python and Pygame** as a Computer Graphics project.

The game features two playable cars, a racing track, keyboard controls, car rotation and movement, collision detection, lap counting, a game timer, and a winner system based on completing two laps.

## Features

* 2-player racing gameplay
* Red and green player cars
* Keyboard-based controls
* Car movement and rotation
* Acceleration and deceleration
* Track boundary collision detection
* Car bouncing when hitting the track border
* Lap counting
* Race timer
* Two-lap winning condition
* Multiple game levels
* Custom graphics and track assets

## Technologies Used

* Python
* Pygame
* Object-Oriented Programming
* 2D Computer Graphics
* Collision Detection
* Image Transformation

## Project Structure

```text
computer-graphics-car-race/
│
├── imgs/
│   ├── red-car.png
│   ├── green-car.png
│   ├── originaltrack.png
│   ├── track_border.png
│   ├── finish.png
│   └── ...
│
├── main.py
├── game_important.py
├── .gitignore
└── README.md
```

## Requirements

* Python 3.x
* Pygame

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/Joshiexzz/computer-graphics-car-race.git
```

### 2. Open the project directory

```bash
cd computer-graphics-car-race
```

### 3. Install Pygame

```bash
pip install pygame
```

### 4. Run the game

```bash
python main.py
```

## Controls

### Player 1 — Red Car

| Key | Action        |
| --- | ------------- |
| `W` | Move forward  |
| `S` | Move backward |
| `A` | Turn left     |
| `D` | Turn right    |

### Player 2 — Green Car

| Key | Action        |
| --- | ------------- |
| `↑` | Move forward  |
| `↓` | Move backward |
| `←` | Turn left     |
| `→` | Turn right    |

The controls are implemented using Pygame keyboard input. Player 1 uses `W/A/S/D`, while Player 2 uses the arrow keys.

## Gameplay

When the game starts, players are prompted to press a key to begin the level.

The game runs at **60 FPS** and continuously updates the screen, player controls, collision detection, timer, and lap information.

### Starting the Race

At the beginning of a level, the game displays a message asking the player to press a key to start.

```text
Press any key to start level 1
```

Once a key is pressed, the race begins.

## Car Movement

The cars use velocity, acceleration, rotation, and trigonometric calculations to control their movement.

The car's direction is converted from degrees to radians, and its horizontal and vertical movement is calculated using sine and cosine.

```text
angle
  │
  ▼
Radians
  │
  ├──► sin(angle) → horizontal movement
  │
  └──► cos(angle) → vertical movement
```

The cars also gradually reduce their speed when the movement keys are not pressed.

## Collision Detection

The game uses **Pygame masks** for pixel-based collision detection.

Masks are created for:

* The track border
* The finish line
* Each car

When a car collides with the track border, its velocity is reversed and reduced, producing a bounce effect.

## Lap System

Each player has an individual lap counter.

When a car crosses the finish line, its lap count increases by one.

The game prevents the same crossing from being counted multiple times using a `crossed_finish` flag.

## Winning Condition

The race is won when a player completes **2 laps**.

### Red Car

```text
Red car Wins after 2 laps!
```

### Green Car

```text
Green car Wins after 2 laps!
```

After displaying the winner, the game resets both cars and starts the game state again.

## Game Information

The game includes a `Game_info` class responsible for managing:

* Current level
* Level start state
* Level start time
* Level progression
* Game completion

The project currently defines **8 levels** in the game configuration.

## Computer Graphics Concepts

This project demonstrates several important Computer Graphics concepts:

### 1. 2D Transformation

The cars are rotated using Pygame's image transformation functionality.

```python
pygame.transform.rotate(image, angle)
```

The project also scales images to appropriate sizes before displaying them.

### 2. Translation

The position of each car is continuously updated using its calculated horizontal and vertical movement.

### 3. Rotation

Players can rotate their cars left and right while racing.

### 4. Collision Detection

Pygame masks are used to detect collisions between the cars and track boundaries.

### 5. Animation

The game continuously updates and redraws the cars and track inside the main game loop.

### 6. Coordinate System

The game uses the screen's X and Y coordinates to determine the position of the cars and other game elements.

## Main Classes and Functions

### `AbstractCar`

Provides the common functionality for the racing cars, including:

* Movement
* Rotation
* Acceleration
* Deceleration
* Collision detection
* Resetting
* Bouncing

### `Player_car1`

Represents the red car.

### `Player_car2`

Represents the green car.

Both player classes inherit the common functionality from `AbstractCar`.

### `Game_info`

Manages the game level, start time, level progression, and game completion state.

### `control_of_player1()`

Handles keyboard input for Player 1.

### `control_of_player2()`

Handles keyboard input for Player 2.

### `handle_collision()`

Handles track collisions, finish-line detection, lap counting, and determining the winner.

## Game Loop

The main game loop continuously performs the following operations:

```text
Start Game
    │
    ▼
Initialize Pygame
    │
    ▼
Load Track & Car Images
    │
    ▼
Create Players
    │
    ▼
Start Level
    │
    ▼
Read Keyboard Input
    │
    ▼
Move & Rotate Cars
    │
    ▼
Check Collisions
    │
    ▼
Update Laps & Timer
    │
    ▼
Check Winner
    │
    ▼
Draw Game
    │
    └──────────────► Repeat
```

## Future Improvements

* Add more racing tracks
* Add additional levels
* Add sound effects and background music
* Add a main menu
* Add a restart button
* Add a pause system
* Improve graphics and animations
* Add more players or AI-controlled opponents
* Add a scoreboard
* Add improved collision handling
* Add a final race results screen

## Author

**Abhinav Joshi**

GitHub:
https://github.com/Joshiexzz

## License

This project was developed for educational purposes as part of a Computer Graphics project.
