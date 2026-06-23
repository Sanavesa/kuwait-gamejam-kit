---
description: Save your progress as a checkpoint
argument-hint: (optional) a short name for this save point
---
Save my current progress as a checkpoint (a git commit), clean and beginner-safe.

- **If git isn't set up yet:** `git init`, set a **local** git identity if none exists (`git config --local user.name`/`user.email`, a sensible default) so the commit can't fail, and add a small `.gitignore` for OS/editor junk (plus `submission/`, the `/submit` build output).
- **Stage the game's files** (`git add -A`), but don't commit obviously unneeded or huge files.
- **Commit with a concise, descriptive message**: short, imperative, present tense, e.g. *"Add score and lives"*, *"Tune jump feel"*, *"Fix restart bug"* (not *"stuff"* or a whole paragraph). Use my text in "$ARGUMENTS" as the message; if I gave nothing, summarize what actually changed in a few words. Aim to make each checkpoint a **working state**.
- Keep it **local**; don't push to any remote unless I ask.

Then **tell me the exact name you saved it under** (echo the commit message back, e.g. *Saved checkpoint: "Add score and lives"*) so I know what this save point is called; I'll use that name to `/undo` later. Finally, list my recent checkpoints (most recent first, one short line each with how long ago) so I can see my save points at a glance.
