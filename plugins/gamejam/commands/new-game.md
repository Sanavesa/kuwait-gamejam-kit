---
description: Start a new single-file browser game from a one-line idea
argument-hint: <one line describing your game>
---
Create a complete, self-contained HTML5 game in a single file named **index.html** based on this idea:

$ARGUMENTS

Requirements:
- **Start as a single file** (HTML, CSS, and JavaScript inline) so it runs by just opening `index.html` — no external files, no build step. (We can split into more files later if the idea grows; for now, keep it simple.)
- **Plain vanilla JS — don't pull in a library for this.** A single-file Canvas game doesn't need one, and skipping it keeps everything self-contained with nothing extra to break. (If a library ever *is* worth it, **save the file into the folder** rather than hot-linking a CDN, so a slow or down CDN can't break the game when a judge plays.)
- Use a `<canvas>` element. Keep the code clean and lightly commented.
- Include clear controls and a simple start state the player understands immediately. Use a **"click/press to start"** gate so the first interaction begins the game — this also grabs keyboard focus and (later) lets audio play inside itch.io's iframe.
- **`preventDefault()` on the game's keys** (especially arrows and space) so they move the player instead of scrolling the page when the game is embedded.
- Make it visually clean but **simple** — we add polish and "juice" later.

After creating it: tell me exactly how to run it and what the controls are. Then **set up version control properly**: run `git init`; if no git identity is configured, set a **local** one (`git config --local user.name`/`user.email`, a sensible default) so commits never fail; add a small `.gitignore` (OS/editor junk like `.DS_Store`, `Thumbs.db`, temp files); then make the first commit with a clear, concise message (e.g. `Initial game`). Keep everything **local** — don't push anywhere. Finally, suggest I run **/brief** to write a short game brief so you remember the plan as we build.
