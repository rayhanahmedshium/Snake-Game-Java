# Snake Game in Java

The classic Snake arcade game, built from scratch in Java with the Swing GUI toolkit. I wrote this to practice object-oriented programming, event handling, and game loop design.

## Features

- Arrow-key controls, with a guard that stops the snake from reversing into itself
- Three speed levels (Slow, Normal, Fast) chosen at start
- Score counter: +10 per food
- Collision detection for walls and the snake's own body
- Game over screen with instant restart (press SPACE)

## How to run

You need Java 8 or newer.

**From the command line**
```bash
javac SnakeGame.java
java SnakeGame
```

**In BlueJ**
Open the folder as a project, compile, then right-click `SnakeGame` and run `main`.

## Controls

| Key | Action |
|---|---|
| Arrow keys | Change direction |
| Space | Restart after game over |

## How it works

- **Game loop:** a `javax.swing.Timer` fires every 100-200 ms depending on the chosen speed. Each tick calls `move()`, `checkFood()`, `checkCollision()`, then `repaint()`.
- **Snake storage:** two arrays hold the x and y position of every body segment. Moving shifts each segment into the position of the one ahead of it, then moves the head one tile.
- **Input:** a `KeyAdapter` updates the direction, ignoring the key that would make the snake turn back on itself.
- **Drawing:** `paintComponent()` draws the food, the snake (green head, cyan body), and the score.

## What I'd improve next

- Stop food from spawning on top of the snake's body
- Save a high score between games
- Add a pause key
- Split the code into separate classes (`Snake`, `Food`, `GamePanel`) for cleaner design

## Built with

Java, Swing, BlueJ
