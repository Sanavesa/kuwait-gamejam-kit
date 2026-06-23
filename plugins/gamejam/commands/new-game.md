---
description: Shape a game idea with me, then build it into a playable browser game
argument-hint: <one line describing your game (or the jam theme)>
---
Help me turn this into a small, finishable browser game:

$ARGUMENTS

If a **`CLAUDE.md` game brief already exists** (e.g. from a past session), read it first and build from it, combined with the idea above, then skip straight to building.

**First, a quick brainstorm, then build.** Don't build blindly. Open a short dialogue to shape the idea, then make the game. Keep it tight: a few small batches of questions (2–3 at a time), wait for my answers between them, and **always offer answer options as a short lettered list (a–d) with a "something else" escape**, and I can still type my own.

Keep questions **about the game**, not about me. Lock down:
- the **one core mechanic**: the single thing I do over and over;
- the **feeling** I'm going for (e.g. *(a)* tense challenge · *(b)* cozy/relaxing · *(c)* satisfying movement · *(d)* discovery · *(e)* score-chasing);
- **win/lose** and the **look & feel** (palette, vibe);
- if there's a jam theme, **how it visibly shows up in the mechanic** (not just the art).

**Clarify anything ambiguous before you build it.** If a requirement could go several ways, ask, with options. Don't silently guess. Recommend the **smallest version that's still fun**, but let me decide. When the idea is clear enough to build, say so and go.

**Build it right for a jam:**
- **One self-contained file** (HTML, CSS, and JS inline) so it runs by just opening `index.html`. No build step, no external files. (It can grow into more files later; keep it simple for now.)
- **Plain vanilla JS, no libraries.** A single-file canvas game doesn't need one, and skipping it keeps everything self-contained. (If a library ever earns its place, save it into the folder rather than hot-linking a CDN that could be down when a judge plays.)
- Use a `<canvas>`, and keep the code clean and lightly commented.
- **Responsive and crisp from the start** (a default, not an afterthought): run the game logic at a **fixed virtual resolution** and scale only the rendering to fit the window, keeping the **aspect ratio** (letterbox/pillarbox, never stretch) so speeds don't change with screen size. Handle **`devicePixelRatio`** so it stays sharp on high-DPI screens. Update on **resize / orientation change without resetting** the game, and make sure it fits inside an **itch.io iframe**.
- **A "click / press to start" gate** for the first interaction: it begins the game, grabs keyboard focus, and later lets audio play inside the iframe.
- **`preventDefault()` on the game's keys** (arrows, space) so they drive the game instead of scrolling the page.
- Keep visuals **clean and simple**; polish comes later via `/polish`.

**After building it:**
- Tell me exactly **how to run it** and what the **controls** are.
- Make sure a short **`CLAUDE.md` game brief** exists: create it, or refresh an existing one (read it and update rather than overwrite; keep any "How to work with me, Claude" section). Cover what the game is, the one core mechanic, controls, look & feel, theme, and win/lose, plus a brief **"How to work with me, Claude"** section (build in small steps; default to a single self-contained `index.html`; keep it iframe-safe; generate art and audio in code; treat git commits as save points; offer numbered options when asking me questions; keep this brief in sync yourself). Claude reads this file every session, so I never have to re-explain. Keep it short, and tell me I can update it anytime with *"update the game brief: …"*.
- **Set up version control:** run `git init`; if no git identity is set, configure a **local** one (`git config --local user.name`/`user.email`) so commits never fail; add a small `.gitignore` (OS/editor junk); then make the first commit (including `index.html`, `CLAUDE.md`, and `.gitignore`) with a clear message like `Initial game`. Keep everything **local**; don't push.
- Finally, suggest I **open it and play**, then run `/polish` when I want it to feel good, or just ask for the next feature.
