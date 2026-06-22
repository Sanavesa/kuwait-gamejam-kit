---
description: Build a complete browser game from a one-line idea
argument-hint: <one line describing your game>
---
Create a complete, self-contained HTML5 game in a single file named **index.html** from this idea:

$ARGUMENTS

If a **`CLAUDE.md` game brief already exists** (e.g. from `/brainstorm`), read it first and build from it, combined with the idea above.

**Build it right for a jam:**
- **One self-contained file** — HTML, CSS, and JS inline — so it runs by just opening `index.html`. No build step, no external files. (It can grow into more files later; keep it simple for now.)
- **Plain vanilla JS, no libraries.** A single-file canvas game doesn't need one, and skipping it keeps everything self-contained. (If a library ever earns its place, save it into the folder rather than hot-linking a CDN that could be down when a judge plays.)
- Use a `<canvas>`, and keep the code clean and lightly commented.
- **Responsive and crisp from the start** (a default, not an afterthought): run the game logic at a **fixed virtual resolution** and scale only the rendering to fit the window, keeping the **aspect ratio** (letterbox/pillarbox, never stretch) so speeds don't change with screen size. Handle **`devicePixelRatio`** so it stays sharp on high-DPI screens. Update on **resize / orientation change without resetting** the game, and make sure it fits inside an **itch.io iframe**.
- **A "click / press to start" gate** for the first interaction — it begins the game, grabs keyboard focus, and later lets audio play inside the iframe.
- **`preventDefault()` on the game's keys** (arrows, space) so they drive the game instead of scrolling the page.
- Keep visuals **clean and simple** — polish comes later via `/polish`.

**After building it:**
- Tell me exactly **how to run it** and what the **controls** are.
- Make sure a short **`CLAUDE.md` game brief** exists — create it, or refresh the one `/brainstorm` saved. Cover what the game is, the one core mechanic, controls, look & feel, theme, and win/lose, plus a brief **"How to work with me, Claude"** section (build in small steps; default to a single self-contained `index.html`; keep it iframe-safe; generate art and audio in code; treat git commits as save points; offer numbered options when asking me questions; keep this brief in sync yourself). Claude reads this file every session, so I never have to re-explain. Keep it short, and tell me I can update it anytime with *"update the game brief: …"*.
- **Set up version control:** run `git init`; if no git identity is set, configure a **local** one (`git config --local user.name`/`user.email`) so commits never fail; add a small `.gitignore` (OS/editor junk); then make the first commit — including `index.html`, `CLAUDE.md`, and `.gitignore` — with a clear message like `Initial game`. Keep everything **local**; don't push.
- Finally, suggest I **open it and play**, then run `/polish` when I want it to feel good — or just ask for the next feature.
