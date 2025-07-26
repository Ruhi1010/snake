# 🐍 Snake Game 

This documentation breaks down the structure, logic, and features of a modern-styled Snake game built using `pygame`.

---

## 📦 Imports & Initialization

```python
import pygame
import sys
import random
import math

pygame.init()
```

- **pygame**: Handles rendering, input, and game loop.
- **sys**: Used to exit the game cleanly.
- **random**: Generates random positions for food.
- **math**: Used for visual effects (e.g., pulsing).

---

## ⚙️ Constants

```python
WINDOW_WIDTH = 800
WINDOW_HEIGHT = 600
GRID_SIZE = 20
GRID_WIDTH = WINDOW_WIDTH // GRID_SIZE
GRID_HEIGHT = WINDOW_HEIGHT // GRID_SIZE
```

- Defines the screen size and how many grid cells the snake and food will occupy.

### 🎨 Color Palette

```python
COLORS = {
    'background': (18, 18, 18),
    'grid': (35, 35, 35),
    'snake_head': (76, 175, 80),
    'snake_body': (56, 142, 60),
    'food': (244, 67, 54),
    'text': (255, 255, 255),
    'accent': (103, 58, 183),
    'game_over': (255, 82, 82),
    'shadow': (0, 0, 0, 100)
}
```

- Defines a modern and minimalistic color palette.

---

## 🐍 `Snake` Class

Handles snake position, movement, and collision logic.

```python
class Snake:
    def __init__(self):
        self.positions = [(GRID_WIDTH // 2, GRID_HEIGHT // 2)]
        self.direction = (1, 0)
        self.grow = False
```

- Snake starts at the center and moves right.

### Movement and Collision

```python
def move(self):
    ...
```

- Moves the snake.
- Detects collision with wall or self.
- Grows if `self.grow` is `True`.

### Direction Control

```python
def change_direction(self, direction):
    ...
```

- Prevents reversing directly into itself.

### Grow Trigger

```python
def eat_food(self):
    self.grow = True
```

- Sets flag to grow on next move.

---

## 🍎 `Food` Class

Represents the food object.

```python
class Food:
    def __init__(self, snake_positions):
        ...
```

- Ensures food is not placed on the snake.

### Position Generation

```python
def generate_position(self, snake_positions):
    ...
```

- Randomly chooses an empty cell.

### Animation

```python
def update(self):
    self.pulse += 0.2
```

- Increments pulse for the pulsing effect.

---

## 🎮 `Game` Class

Handles game state, input, rendering, and loop.

### Initialization

```python
class Game:
    def __init__(self):
        ...
```

- Sets up display, fonts, and resets game.

### Game Reset

```python
def reset_game(self):
    ...
```

- Creates new snake and food.
- Resets score and state flags.

---

## 🎮 Input Handling

```python
def handle_events(self):
    ...
```

- Arrow keys: movement  
- `SPACE`: pause/unpause or restart after game over  
- `R`: reset after game over  
- `QUIT`: exit game

---

## 🔁 Game Update

```python
def update(self):
    ...
```

- Moves snake  
- Checks for collisions  
- Checks if food is eaten  
- Updates food animation

---

## 🧱 Grid Rendering

```python
def draw_grid(self):
    ...
```

- Draws subtle grid background.

---

## 🐍 Snake Rendering

```python
def draw_snake(self):
    ...
```

- Renders:
  - Shadow under head
  - Snake head with eyes in the direction of movement
  - Snake body with fading segments

---

## 🍎 Food Rendering

```python
def draw_food(self):
    ...
```

- Renders:
  - Pulsing animation
  - Shadow
  - Shine effect

---

## 🖥️ UI Rendering

```python
def draw_ui(self):
    ...
```

- Displays:
  - Score
  - Instructions
  - Game Over screen with overlay and restart option
  - Paused screen

---

## 🖼️ Frame Rendering

```python
def draw(self):
    ...
```

- Clears screen
- Draws grid, snake, food, and UI
- Updates the display

---

## 🕹️ Main Game Loop

```python
def run(self):
    ...
```

- Handles events
- Updates and draws each frame
- Runs at 10 FPS

---

## 🚀 Entry Point

```python
if __name__ == "__main__":
    game = Game()
    game.run()
```

- Starts the game when the script is run.

---

## ✅ Features Summary

| Feature              | Description |
|----------------------|-------------|
| Snake & Food         | Classic grid-based gameplay |
| Game Over Detection  | Wall & self collision |
| Modern UI            | Gradient, shadows, and polished colors |
| Animation Effects    | Pulsing food, snake fade |
| Pause & Restart      | SPACE and R keys |
| Responsive Input     | Smooth direction changes |

---

