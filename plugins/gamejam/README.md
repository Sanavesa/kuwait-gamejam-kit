# Game Jam Kit (plugin)

Beginner-friendly Claude Code commands for building HTML5 games in a 72-hour jam. No engine, no build tools, just one self-contained `index.html`, shipped to itch.io.

## Commands (5)

| Command | What it does |
|---|---|
| `/new-game <idea>` | Brainstorm the idea with you, then build a complete single-file browser game and set up your first save point. |
| `/save [name]` | Save your progress as a checkpoint you can return to. |
| `/undo [name]` | Roll back to a working checkpoint. |
| `/fix <error>` | Fix a bug from a console error or a description. |
| `/submit` | Package the game for itch.io and write your page text. |

**Art, sound, and polish need no command:** just ask (or let Claude offer), and it generates art and sound in code and adds game-feel juice from a menu, as part of building, every session. To use **your own** asset, drop the file in the **`assets/` folder** and reference it as `@assets/name.png` when you ask.

Install and full docs: see the [marketplace README](../../README.md).
