---
description: Package the game as a zip ready to upload to itch.io
---
Get my game ready to submit to the itch.io jam:

1. **Quick pre-flight:** make sure the game actually runs (no console errors), and save a `/checkpoint` first so the submitted version is saved. If we haven't tried it recently, remind me to **play a full round myself first** (and hand it to someone else to play) so I catch anything broken before judges do.
2. Confirm the playable file is named **index.html**. itch serves the game online, so CDN links *do* load — but for reliability at judging time, prefer **self-contained**: if the game hot-links any third-party script/font, consider **vendoring it into the zip** so a slow or down CDN can't break it. If the main file has another name, tell me — itch.io needs `index.html`.
3. Create a **zip** with `index.html` at the **root of the zip** (NOT inside a subfolder), including any asset files the game needs.
4. Tell me the exact name and location of the zip file.

Then print this submission checklist for me to follow on itch.io:
- [ ] Upload the zip to the jam submission.
- [ ] Tick **"This file will be played in the browser."**
- [ ] Fill in **title, short description, controls, and credits** (list any assets I used).
- [ ] Submit.
- [ ] Open the game **from the jam page** and confirm it actually plays.

Remind me: upload a working version **early**, then re-run this command to re-zip as I keep polishing.
