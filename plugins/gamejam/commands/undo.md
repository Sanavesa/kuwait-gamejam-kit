---
description: Go back to your last working checkpoint (undo recent changes)
argument-hint: (optional) name of the checkpoint to return to
---
I want to undo my recent changes and go back to a saved checkpoint — do it the **safe, non-destructive** way (never delete my saved history).

- First warn me in ONE short line that this discards my **uncommitted** changes since that checkpoint.
- Target: if I named a checkpoint in "$ARGUMENTS", use it; otherwise the most recent one.
- **Restore the working files without rewriting history:** to drop just the latest uncommitted edits, use `git restore .` (or `git checkout -- .`); to return to an **older** checkpoint, bring its files back with `git checkout <commit> -- .` — so every checkpoint still exists and I can go forward again.
- **Do not** `git reset --hard` away my commits, delete history, or touch any remote.

Then tell me which checkpoint we're now on and remind me to run the game to confirm it's back to working.
