# Game Jam Kit (plugin)

Beginner-friendly Claude Code commands for building HTML5 games in a 72-hour jam. No engine, no build tools, just one self-contained `index.html`, shipped to itch.io.

## Commands (4)

| Command | What it does |
|---|---|
| `/new-game <idea>` | Brainstorm the idea with you, then build a complete single-file browser game and set up your first save point. |
| `/save [label]` | Save your progress as a versioned checkpoint (`v1`, `v2`, ...) with an optional label. |
| `/undo [version/label]` | Roll back to a checkpoint by version (e.g. `v3`), by label, or your last save if omitted, after confirming with you first. |
| `/submit` | Package the game for itch.io and write your page text. |

**Art, sound, polish, and bug-fixing need no command:** just ask (or paste an error / let Claude offer). It generates art and sound in code, adds game-feel juice from a menu, and fixes bugs from a console error or your description, as part of building, every session. To **play**, just open `index.html` in your browser (double-click it). To use **your own** asset, drop the file in the **`assets/` folder** and reference it as `@assets/name.png` when you ask.

Install and full docs: see the [marketplace README](../../README.md).
