# Pac-Man

Classic arcade Pac-Man game built with vanilla JavaScript. Navigate the maze, eat pellets, avoid ghosts, and rack up points!

[Play the game](https://bborbe.github.io/pacman/) (GitHub Pages placeholder)

## Features

- Classic 28x31 tile maze layout
- Smooth tile-based movement with pixel interpolation
- 4 ghosts with chase AI (Blinky, Pinky, Inky, Clyde)
- Power pellets that make ghosts vulnerable
- Tunnel wrap-around on sides
- 3 lives system
- Score tracking with localStorage persistence
- Pause and restart functionality
- Ready screen countdown
- Victory screen when level complete

## How to Play

Navigate Pac-Man through the maze eating all pellets while avoiding ghosts. Eat power pellets to turn ghosts blue and vulnerable - then chase them down for bonus points!

## Controls

- **Arrow Keys** - Move Pac-Man (up, down, left, right)
- **P / Esc** - Pause/unpause game
- **R** - Restart game

## Scoring

- **Pellet** - 10 points
- **Power Pellet** - 50 points
- **Eating Ghosts** - 200, 400, 800, 1600 points (cascading during single power pellet)

Complete the level by eating all 244 pellets!

## Technical Details

- Single HTML file with embedded CSS and JavaScript
- Modular architecture:
  - `createGameState()` - Game logic, collision detection, AI
  - `createRenderer()` - Canvas rendering
  - `createInputHandler()` - Keyboard input
- requestAnimationFrame game loop
- localStorage for high score persistence
- Classic Pac-Man color palette and styling

## Game States

- **Ready** - 3-second countdown before game starts
- **Playing** - Active gameplay
- **Paused** - Game frozen, can resume
- **Game Over** - All lives lost
- **Victory** - All pellets collected

## Ghost Behavior

- **Chase Mode** - Ghosts move toward Pac-Man's position
- **Frightened Mode** - Ghosts turn blue and move randomly (triggered by power pellet)
- **Eaten Mode** - Ghost returns quickly to ghost house after being eaten

## Browser Compatibility

Works in all modern browsers with HTML5 Canvas support.
