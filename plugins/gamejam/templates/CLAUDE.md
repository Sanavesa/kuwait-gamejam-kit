# Game Brief

> Claude Code reads this file automatically at the start of every session, so it always remembers what you're building. Keep it short. **Claude keeps this brief in sync for you** — when the game changes in a way that affects what's written here, it updates this file as part of that change. (You can always nudge it too: *"update the game brief: the theme is underwater."*) A good brief keeps your game consistent and saves your usage quota (you stop re-explaining).

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
**You are my expert game-dev pair. I'm a beginner — keep it simple, keep me moving, and use your full toolkit.**

- **When you ask me something, give me choices.** If a question has a few likely answers, lay them out as a short **numbered list (2–4 options) with a recommended default first** so I can just reply with a number — don't leave it open-ended. I'm a beginner; picking is far easier than composing an answer from scratch. Save open-ended questions for when they're genuinely needed.

Structure & tech:
- **Default to a single self-contained `index.html`** (HTML + CSS + JS inline) so it runs by just opening the file. **It's OK to grow into multiple files** if the idea needs it — keep `index.html` as the entry point and set up a **simple local preview** (a tiny local server) so it still runs (multi-file opened directly hits CORS). No heavy build tools (npm/bundlers) unless I ask.
- Prefer simple, readable code; comment lightly. Generate audio/art **in code** when reasonable so nothing has to be downloaded.

How to build:
- Work **one small step at a time**; after each change, remind me to **run it, play it, and `/checkpoint`** if I like it.
- **When I ask to add a feature**, do it the jam-safe way: if I've got unsaved progress worth keeping, suggest a quick `/checkpoint` first so we can `/undo` if it goes wrong. **Scope-check it** — build the *smallest version that adds the fun*, resist scope creep (offer to defer the extras as "Could"), and **never break the playable build** (layer the feature in around what already works). Mind the pitfalls on anything new: reset its state on restart, cap object counts / keep one animation loop, `preventDefault()` any new keys, keep it iframe/responsive-safe. Then have me run + play it, and suggest `/checkpoint` if it's good (or `/undo` if not) — and offer to `/juice` or `/sound` the new action.
- **Version control = my save points.** Use git locally (set a local identity if none exists so commits never fail; add a small `.gitignore`). Make **concise, meaningful commits** — short imperative messages like *"Add score"*, *"Fix restart bug"* — each one a working state. Roll back **non-destructively** (restore files; never delete my checkpoint history) and stay **local** (don't push unless I ask).
- **Keep this brief current yourself.** When a change meaningfully alters what's written above (the core mechanic, controls, win/lose, look & feel, or theme), update this `CLAUDE.md` as part of that change and tell me in one line — don't wait for me to ask. Skip it for small tweaks; the brief should stay short and stable, not churn every turn.
- "**Ugly first, plays well second, pretty last.**" Get the core loop fun before making it pretty or big.
- Proactively **suggest the right kit command** for what I'm doing (e.g. `/juice`, `/sound`, `/art`, `/submit`).
- For a stubborn bug, debug systematically (reproduce → isolate → smallest fix → verify).

Quality bar:
- Keep performance smooth: cap particle/object counts, reuse objects instead of creating thousands, one `requestAnimationFrame` loop, and **reset all state cleanly on restart**.
- **Keep it responsive and crisp by default** (maintain this as the game grows, don't bolt it on at the end): run logic in a fixed virtual resolution and scale only the rendering to fit the window while keeping aspect ratio, handle `devicePixelRatio` so it's never blurry, and update on resize without resetting. Offer touch controls + a fullscreen toggle later if the game suits a phone.
- **Make it survive the itch.io iframe** (where judges play): wrap any `localStorage` use in `try/catch` with an in-memory fallback (it can throw in the sandboxed iframe), `preventDefault()` on the game's keys (arrows/space) so they drive the game instead of scrolling the page, and make sure the first click/keypress both focuses the game **and** resumes audio.
- **Build the game shell — cheap presentation points beginners skip.** When the game has no front-end, proactively offer to add one, built as clean game **states** (e.g. `MENU / PLAYING / PAUSED / GAMEOVER`) rather than everything at once: a **title screen** + how-to-play, **pause** (P/Esc) that truly freezes, and a **game-over** screen with **restart that fully resets state** and a **high score** (wrapped in the `try/catch` iframe rule above). Add smooth transitions so it feels finished.
- If something breaks, make the **smallest fix** that works and explain what was wrong in one plain sentence.
- Remind me to **credit any third-party/AI assets** and to **upload a working build early**.
