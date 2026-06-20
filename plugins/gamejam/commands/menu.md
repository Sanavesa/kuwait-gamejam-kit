---
description: Add a complete game flow — title, how-to-play, pause, game over, restart
argument-hint: (optional) the game's name / any flow you want
---
Add a clean, complete **game flow** around my game — cheap **Presentation** points that judges reward and beginners skip. Don't break existing gameplay; layer this around it as proper game states.

Implement (adapt to my game; ask the title if I didn't give one in "$ARGUMENTS"):
- A **title screen**: game name, a short tagline, and a clear **Start** (click or key). Make it look intentional — consistent font + palette, maybe a subtle animated background.
- **How-to-play:** one or two lines of controls + goal, on the title screen or a quick first-time overlay.
- A real **state system** (e.g. `MENU / PLAYING / PAUSED / GAMEOVER`) so screens transition cleanly instead of everything running at once.
- **Pause** (P or Esc) that truly freezes the game and shows "Paused".
- A **Game Over** screen: final score, **high score persisted with `localStorage`**, and a **Restart** that **fully resets state** — watch for leftover variables, timers, and intervals; reset cleanly so round 2 isn't buggy. **Wrap every `localStorage` read/write in `try/catch` with an in-memory fallback** — itch.io runs the game in a sandboxed iframe where `localStorage` can throw a `SecurityError` (Safari, and Chrome with third-party-storage blocking); unguarded, that crashes the whole game on a judge's machine. A failed save should silently fall back to a session-only high score, never break the game.
- Smooth **transitions** (a quick fade/slide) so it feels finished.

Use a **readable font** — a clean system-font stack is simplest and has zero dependencies; a Google Font is fine too, but give it a **system fallback** so the game still looks right if the font is slow to load. After implementing, walk me through each screen and remind me to run + `/checkpoint`.
