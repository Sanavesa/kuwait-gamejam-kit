---
description: Package your game and write its itch.io page
argument-hint: (optional) my name/handle, anything to emphasize
---
Get my game fully ready to submit to the itch.io jam: in one pass, produce the **zip**, the **page text**, and the **checklist**.

**1. Quick pre-flight.** Make sure the game actually runs (no console errors), and run `/save` first so the submitted version is saved. If we haven't tried it recently, run it for me (local preview server) and remind me to **play a full round myself first** (and hand it to someone else to play) so I catch anything broken before judges do.
   - **Am I on track to finish?** Is the core loop playable end-to-end *right now* (start → play → win/lose → restart)? If not, that's the only priority; everything else waits. If I'm short on time, help me sort what's left into **"needed to be complete"** vs **"nice to have,"** name the smallest version that's still fun, and flag anything risky to **cut or `/undo`**. Either way: **upload a working build now**, then keep polishing and re-submit.

**2. Build the zip.**
- **Settle the game's name first.** Use the name already in use, the **Title** in my `CLAUDE.md` brief, or the `<title>` in `index.html`. **Only if none exists, ask me** for the game's name (suggest one from the game); don't invent one silently. Use this name for the page title and the made-with info.
- Confirm the playable file is named **index.html**. itch serves the game online, so CDN links *do* load, but for reliability at judging time, prefer **self-contained**: if the game hot-links any third-party script/font, consider **vendoring it into the zip** so a slow or down CDN can't break it. If the main file has another name, tell me, since itch.io needs `index.html`.
- Put all artifacts this command creates in a **`submission/` folder** at the project root (create it if needed), and make sure `submission/` is in `.gitignore` (add it if missing) since it's regenerated build output. Create the **zip as `submission/game.zip`** with `index.html` at the **root of the zip** (NOT inside a subfolder), including the **`assets/` folder** and any other files the game needs.
- Tell me the exact location of `submission/game.zip`.

**3. Write the itch.io page text.** Pull from my `CLAUDE.md` brief and the **actual game** (read the code for controls, mechanics, win/lose, and any assets used). **Get the jam name and theme from my `CLAUDE.md` brief (the "Theme (jam)" section), don't ask me for them**; just mention the theme on the page and flag it as a TO-DO only if the brief truly has nothing. Ask me only for what you genuinely can't infer (e.g. my name/handle, tools I used); use "$ARGUMENTS" for anything I've already told you. Save the page text as **`submission/page.md`** (and still print it for me), **ready to copy-paste**, in this order:
- **Title** + a punchy **one-line tagline**.
- **Premise / pitch** (2–4 sentences): what the game is, the hook, and how it fits the **theme**, written to make a judge want to hit Play. No fluff.
- **How to play:** the goal in one line, then a clear **controls** list (keyboard *and* touch if supported). Cover how to start, the objective, and how you win/lose.
- **Features:** 3–5 short bullets highlighting what's cool (mechanics, game feel, audio, modes).
- **Tips** (optional, 1–2 lines) if the game needs them to be enjoyed.
- **Credits:** me as creator + role, plus **every third-party / AI asset** with its source and license. Scan the project and my notes and **flag anything uncredited as a TO-DO** (crediting is required by the rules).
- **Made with / build info:** engine-free HTML5 + Claude Code, jam name, and the date, plus any tools used.
- **Known issues** (optional, brief & honest): only if there's something a judge will hit.

**4. Publishing checklist.** Print this for me to follow on itch.io:
- Suggested **genre/tags** and a note on the best **screenshot or GIF** to capture (judges scan visuals first, so pick the most exciting moment).
- [ ] Upload **`submission/game.zip`** to the jam submission.
- [ ] Tick **"This file will be played in the browser."**
- [ ] Fill in **title, short description, controls, and credits** (paste from the page text above).
- [ ] Set a **thumbnail/cover** image.
- [ ] **Submit.**
- [ ] Open the game **from the jam page** and confirm it actually plays.

If the game is missing a **title screen, how-to-play, or game-over/restart**, offer to add that game shell now (built as clean game states, with an iframe-safe high score); it's cheap presentation points, and the controls then also appear *inside* the game, not just on the page.

Remind me: upload a working version **early**, then re-run this command to rebuild `submission/game.zip` and refresh `submission/page.md` as I keep polishing.
