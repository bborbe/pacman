# Pac-Man

Classic arcade Pac-Man game built with vanilla JavaScript. Navigate the maze, eat pellets, avoid ghosts, and rack up points!

[Play the game](https://bborbe.github.io/pacman/) (GitHub Pages placeholder)

## Features

- Classic 28x31 tile maze layout
- Smooth tile-based movement with pixel interpolation
- 4 ghosts with chase AI (Blinky, Pinky, Inky, Clyde)
- Power pellets that make ghosts vulnerable (7 seconds duration)
- Tunnel wrap-around on sides
- 3 lives system
- **Top 10 leaderboard** with name input and localStorage persistence
- Clickable high score display to view leaderboard
- **Comprehensive CONFIG system** for tuning game difficulty
- **URL parameter support** to override settings without code changes
- Ghost randomness for less predictable gameplay
- Pause and restart functionality
- Ready screen countdown
- Victory screen when level complete
- Flash effect when eating power pellets

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

## Configuration

Customize gameplay via URL parameters (no code changes needed):

```
?gameSpeed=0.5          # Slow down for beginners (default: 1.0)
?ghostCount=2           # Fewer ghosts (default: 4)
?powerPelletDuration=600 # Longer power-ups (default: 420 frames / 7 seconds)
?ghostRandomness=0.3    # More random ghost movement (default: 0.1)
```

All CONFIG values can be overridden. See source for full list.

## Technical Details

- Single HTML file with embedded CSS and JavaScript
- Modular architecture:
  - `createGameState()` - Game logic, collision detection, AI
  - `createRenderer()` - Canvas rendering
  - `createInputHandler()` - Keyboard input
- requestAnimationFrame game loop with fixed timestep (120 FPS)
- localStorage for leaderboard (top 10) and last player name
- Comprehensive CONFIG object for all game parameters
- URL parameter parsing to override CONFIG values
- Classic Pac-Man color palette and styling

## Game States

- **Ready** - 3-second countdown before game starts
- **Playing** - Active gameplay
- **Paused** - Game frozen, can resume
- **Game Over** - All lives lost
- **Victory** - All pellets collected

## Ghost Behavior

- **Chase Mode** - Ghosts move toward Pac-Man's position (with optional randomness)
- **Scatter Mode** - Ghosts move to corners (with optional randomness)
- **Frightened Mode** - Ghosts turn blue and move randomly (triggered by power pellet)
- **Eaten Mode** - Ghost returns quickly to ghost house after being eaten

Ghost randomness (CONFIG.ghostRandomness) adds unpredictability - default 10% chance to pick random direction instead of optimal path.

## Browser Compatibility

Works in all modern browsers with HTML5 Canvas support.
