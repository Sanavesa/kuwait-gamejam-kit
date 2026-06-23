---
description: Roll back to a working checkpoint
argument-hint: (optional) name of the checkpoint to return to
---
I want to undo my recent changes and go back to a saved checkpoint. Do it the **safe, non-destructive** way (never delete my saved history).

- **Help me pick which checkpoint to go back to.** If I named one in "$ARGUMENTS", use it. Otherwise, **show my recent checkpoints first** (most recent first, each with its name/message and how long ago), and **recommend which one I probably want**, naming it explicitly: usually the most recent checkpoint (my last working save), but if the most recent one is what introduced the problem, suggest the one *before* that.
- **Always confirm with me before rolling back; never undo without my explicit go-ahead.** This is a drastic change, so name the exact checkpoint we'd land on, warn me in ONE short line that it discards my **uncommitted** changes since then, and **wait for me to say yes** before touching any files. Even if I named a checkpoint in "$ARGUMENTS", confirm first.
- **Restore the working files without rewriting history:** to drop just the latest uncommitted edits, use `git restore .` (or `git checkout -- .`); to return to an **older** checkpoint, bring its files back with `git checkout <commit> -- .`, so every checkpoint still exists and I can go forward again.
- **Do not** `git reset --hard` away my commits, delete history, or touch any remote.

Then tell me which checkpoint we're now on and remind me to run the game to confirm it's back to working.
