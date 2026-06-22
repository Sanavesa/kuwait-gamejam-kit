---
description: Fix a bug from a console error or a description
argument-hint: <paste the red console error, or describe the bug>
---
Help me fix this problem with my game:

$ARGUMENTS

Rules:
- If I pasted a browser **console error**, find the root cause and fix it.
- If I only described a **symptom** (e.g. "the player won't move"), and there's no error to work from, tell me in one line how to get the real error (**press F12 → Console tab → copy the red text**), or invite me to drag in a **screenshot** — then proceed with whatever I give you.
- Make the **smallest change** that fixes it. Don't refactor or add features while fixing.
- Explain in **one sentence** what was wrong, in plain language.
- **If a quick fix doesn't hold or the bug is stubborn,** switch to method: **reproduce → hypothesize the cause → isolate the lines → smallest fix → verify nothing else broke.** Watch for the classic beginner-game culprits: state not reset on restart (leftover variables/timers), audio blocked before a user gesture, animation loops stacking (game speeds up after restart), coordinates not scaled for `devicePixelRatio`, using an asset before it loads, or listeners added repeatedly.

Then tell me to run it again and check, and suggest a `/save` once it's confirmed fixed.
