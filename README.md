# TetriX

> A Tetris-inspired desktop game built with Python and Pygame, focused on game-loop design, piece generation, input handling, persistence, and visual/audio effects.

## Current implementation

The game currently includes:

- Seven-piece bag randomization
- Piece movement and rotation
- Soft drop and hard drop
- Hold piece
- Ghost-piece preview
- Next-piece preview
- Line-clear scoring and progressive levels
- Combo scoring
- Pause and game-over states
- Persistent top-10 high scores in `tetris_scores.json`
- Real-time pieces-per-second (PPS) and lines-per-second (LPS) statistics
- Particle effects, flashes, glow effects, screen shake, and animated line clears
- Procedurally generated sound effects

The project is **Tetris-inspired** rather than a claim of exact adherence to an official Tetris ruleset.

## Installation

The current program imports both Pygame and NumPy, so install both:

```bash
python -m pip install pygame numpy
```

Python 3.8+ is recommended.

## Run

```bash
python TetriX.py
```

## Controls

| Key | Action |
|---|---|
| ← / → | Move piece |
| ↓ | Soft drop |
| ↑ | Rotate |
| Space | Hard drop |
| C | Hold piece |
| P | Pause / resume |
| R | Restart after game over |
| Q | Quit after game over |

## Game mechanics

### Scoring

The current scoring values are:

- Single: `100 × level`
- Double: `300 × level`
- Triple: `500 × level`
- Four-line clear: `800 × level`
- Combo bonus: `50 × combo × level`
- Hard-drop bonus: `2 points` per dropped cell

Levels increase every 10 cleared lines, with faster falling speed at higher levels.

### Seven-piece bag

Each bag contains one I, O, T, S, Z, J, and L piece. The bag is shuffled before pieces are consumed, reducing long runs without a given piece.

## Technical structure

The main implementation is centered around:

- `TetrisGame` — game state, event handling, rendering, scoring, and loop management
- `Tetrimino` — piece state, movement, rotation, and collision behavior
- `SoundManager` — procedural audio
- `Particle` — visual effects

The repository is intentionally compact and currently keeps the game logic in a single main Python source file.

## Persistence

High scores are written to `tetris_scores.json` when the game records a score. The file is runtime data rather than required source code.

## Development

A GitHub Actions workflow performs a Python compile check with the project dependencies installed.

The project is a standalone learning/game-development project; there is not currently a comprehensive automated gameplay test suite.

## Known scope

This is a desktop game prototype and learning project. Performance and behavior can vary by operating system, Pygame version, audio backend, and hardware.

## License

See [LICENSE](LICENSE).
