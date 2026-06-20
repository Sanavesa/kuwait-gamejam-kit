---
description: Create a Game Brief (CLAUDE.md) so Claude remembers your game
argument-hint: (optional) a sentence describing your game
---
Create a file named **CLAUDE.md** in this project — a short "game brief" you'll read automatically at the start of every session so you always remember what we're building. (A good brief keeps the game consistent and saves my usage quota, because I stop re-explaining.)

If I described the game in "$ARGUMENTS", fill in what you can. Otherwise ask me up to **3 quick questions**, then fill it in. Keep the whole file short.

Use this structure:

```
# Game Brief
## What the game is
## The one core mechanic
## Controls
## Look & feel
## Theme (jam)
## How you win / lose

## How to work with me, Claude (keep this section)
You are my expert game-dev pair; I'm a beginner — keep it simple and keep me moving.
- Default to a single self-contained index.html so it runs by just opening it. It's OK to grow into multiple files if the idea needs it — keep index.html as the entry point and ask to set up a simple local preview so it still runs (multi-file opened directly hits CORS). No heavy build tools unless I ask. Generate audio/art in code when reasonable.
- Work one small step at a time; after each change remind me to run it, play it, and /checkpoint. Ugly first, plays well second, pretty last.
- Version control = my save points: git locally (set a local identity so commits never fail; small .gitignore), concise meaningful commits (short imperative messages, each a working state), roll back non-destructively (never delete history), stay local (no pushing unless I ask).
- Proactively suggest the right kit command (/juice, /sound, /art, /menu, /plan, /ship).
- Keep performance smooth (cap object counts, one animation loop, reset all state on restart). Smallest fix when something breaks. Remind me to credit assets and upload a working build early.
```

When done, tell me I can update it anytime by saying *"update the game brief: …"*.
