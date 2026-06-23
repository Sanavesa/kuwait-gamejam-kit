---
description: Save your progress as a checkpoint
argument-hint: (optional) a short label for this save point
---
Save my current progress as a checkpoint (a git commit), clean and beginner-safe.

- **If git isn't set up yet:** `git init`, set a **local** git identity if none exists (`git config --local user.name`/`user.email`, a sensible default) so the commit can't fail, and add a small `.gitignore` for OS/editor junk (plus `submission/`, the `/submit` build output).
- **Stage the game's files** (`git add -A`), but don't commit obviously unneeded or huge files.
- **Always prefix the commit message with an increasing version number** (`v1`, `v2`, `v3`, ...). Find the next number from my existing checkpoints: scan the git log for the highest `vN` prefix used so far and add 1 (start at `v1` if there are none). Don't reuse or skip numbers.
- **Add a concise label after the version**, in the form `v3: <label>` (short, imperative, present tense, e.g. *"v3: Add score and lives"*, *"v4: Tune jump feel"*; not *"stuff"* or a whole paragraph). Use my text in "$ARGUMENTS" as the label; if I gave nothing, summarize what actually changed in a few words. (Only if you truly can't tell what changed, the bare version like *"v3"* is acceptable.) Aim to make each checkpoint a **working state**.
- Keep it **local**; don't push to any remote unless I ask.

Then **tell me the exact name you saved it under** (echo the commit message back, e.g. *Saved checkpoint: "v3: Add score and lives"*) so I know what this save point is called; I'll use that version (e.g. `v3`) to `/undo` later. Finally, list my recent checkpoints (most recent first, one short line each with how long ago) so I can see my save points at a glance.
