---
description: Build a complete browser game from a one-line idea
argument-hint: <one line describing your game>
---
Create a complete, self-contained HTML5 game in a single file named **index.html** based on this idea:

$ARGUMENTS

If a **`CLAUDE.md` game brief already exists** (e.g. from `/brainstorm`), read it first and build from it, combining it with anything in the idea above.

Requirements:
- **Start as a single file** (HTML, CSS, and JavaScript inline) so it runs by just opening `index.html` — no external files, no build step. (We can split into more files later if the idea grows; for now, keep it simple.)
- **Plain vanilla JS — don't pull in a library for this.** A single-file Canvas game doesn't need one, and skipping it keeps everything self-contained with nothing extra to break. (If a library ever *is* worth it, **save the file into the folder** rather than hot-linking a CDN, so a slow or down CDN can't break the game when a judge plays.)
- Use a `<canvas>` element. Keep the code clean and lightly commented.
- **Make it responsive and crisp from the start** (this is a default, not an afterthought): run the game logic in a **fixed virtual resolution** and scale only the *rendering* to fit the window while keeping the **aspect ratio** (letterbox/pillarbox, never stretch), so physics and speeds don't change with screen size. Handle **`devicePixelRatio`** so it isn't blurry on high-DPI screens (`image-rendering: pixelated` for pixel art). Update on **resize / orientation change without resetting** the game. Make sure it works embedded in an **itch.io iframe** (fit the frame, don't assume full window).
- Include clear controls and a simple start state the player understands immediately. Use a **"click/press to start"** gate so the first interaction begins the game — this also grabs keyboard focus and (later) lets audio play inside itch.io's iframe.
- **`preventDefault()` on the game's keys** (especially arrows and space) so they move the player instead of scrolling the page when the game is embedded.
- Make it visually clean but **simple** — we add polish and "juice" later. (Touch controls and a fullscreen toggle aren't needed yet — offer them later if the game suits a phone.)

After creating it: tell me exactly how to run it and what the controls are. Since you now know what we're building, **make sure there's a short game brief in `CLAUDE.md`** — create it, or fill in/refresh the one `/brainstorm` already saved — covering what the game is, the one core mechanic, controls, look & feel, theme, win/lose, plus a "How to work with me, Claude" section (keep it simple, work in small steps, default to a single self-contained `index.html`, version control as save points, generate audio/art in code, make it survive the itch.io iframe, **keep this brief in sync yourself as the game changes**, and **when asking me a question, offer a short numbered list of options to pick from** instead of open-ended questions). This file is read automatically every session so you remember the plan and I never have to re-explain. Keep it short, and tell me I can update it anytime by saying *"update the game brief: …"*.

Then **set up version control properly**: run `git init`; if no git identity is configured, set a **local** one (`git config --local user.name`/`user.email`, a sensible default) so commits never fail; add a small `.gitignore` (OS/editor junk like `.DS_Store`, `Thumbs.db`, temp files); then make the first commit — **including `index.html`, `CLAUDE.md`, and `.gitignore`** — with a clear, concise message (e.g. `Initial game`). Keep everything **local** — don't push anywhere.
