# Game Brief

> Claude Code reads this file automatically at the start of every session, so it always remembers what you're building. Keep it short. **Claude keeps it in sync for you:** when the game changes in a way that affects what's written here, it updates this file as part of that change. You can also nudge it any time — *"update the game brief: the theme is underwater."* A good brief keeps your game consistent and saves you re-explaining.

## What the game is
<One or two sentences. e.g. "A one-button game where you tap to flap through gaps in falling pipes.">

## The one core mechanic
<The single thing that makes it fun. e.g. "Tight, satisfying jumps with risky near-misses.">

## Controls
<e.g. "Arrow keys to move, Spacebar to jump. Click to start.">

## Look & feel
<e.g. "Neon cyberpunk: dark background, glowing pink player, cyan obstacles, chunky retro font.">

## Theme (jam)
<The jam theme, and one line on how this game fits it.>

## How you win / lose
<Short. e.g. "Score points by surviving; one hit ends the run; beat your high score.">

---

## How to work with me, Claude (don't delete this section)
**You're my expert game-dev pair and I'm a beginner — keep it simple, keep me moving, and use your full toolkit.** The Game Jam Kit primer already hands you the technical defaults every session (keep the game itch.io-iframe-safe and crisply scaled, audio only after a gesture, one clean game loop, reset state on restart). This section is just how I like to work:

- **Build in small steps.** After each change, have me run and play it, then suggest `/save` if I like it. For a new feature, build the smallest version that's fun, don't break what already works, and suggest a `/save` before and after.
- **When you ask me something, give me numbered options** (2–4, recommended first) so I can just reply with a number, and **quietly accept more than one** when answers can combine (no need to point out that I can). I'm a beginner — picking beats composing an answer from scratch.
- **Art, sound, polish, and bug-fixing need no command — just do them as we build.** Generate art and sound in code; once the core loop is fun, offer a short menu of juice effects for me to pick from. To use my own asset, I drop it in the **`assets/` folder** and reference it as `@assets/name`. To play, I just open `index.html` in my browser (I hard-refresh with **Ctrl/Cmd+Shift+R** if a change doesn't show up).
- **When I paste a console error or describe what's wrong,** find the root cause, make the smallest fix, and tell me in one sentence what was wrong. No error handy? Tell me to press **F12 → Console → copy the red text**, or I'll drag in a screenshot.
- **`/save` and `/undo` are my save points** — handle whatever runs them behind the scenes; I don't need to hear about git or commits. Keep each save a small working state, stay local, and roll back without ever losing one.
- **Keep this brief current yourself** when the game changes meaningfully (don't churn it on small tweaks), and tell me in one line.
- **Ugly first, plays well second, pretty last.** Get the core loop fun before making it pretty or big. Default to a single self-contained `index.html`; it can grow into more files if the game needs it.
