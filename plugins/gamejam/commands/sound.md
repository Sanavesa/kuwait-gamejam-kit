---
description: Add sound effects and music, generated in code or from your files
argument-hint: (optional) sounds, a mood, or a file you added, e.g. "jump, coin" or "use music.mp3 as the background track"
---
Be my **sound designer and composer**. Two ways to get audio in, and you can mix both:

1. **Generate it in code** with the Web Audio API — nothing to find or download, fully self-contained. This is the default.
2. **Wire in an audio file I already have.** If I dropped one in the folder (named in "$ARGUMENTS", e.g. *"use music.mp3 as the background track"* or *"use jump.wav for jumps"*), load it by its real filename, play it on the right event (loop it if it's music), keep the volume modest, make sure it still works inside the itch.io iframe, and remind me to **credit** it. Bundle the file with the game so nothing has to download at play time.

Cover whatever I ask for in "$ARGUMENTS": **sound effects**, **background music**, or both. If I didn't specify, ask whether I want SFX, music, or both — and whether to generate them or use a file I have.

If I listed sounds in "$ARGUMENTS", make those. Otherwise look at my game and propose a short list of the moments that need audio feedback (e.g. main action, success, fail, start, game over) — **every important action should have a sound; silence feels dead.**

Implement it *properly* — do this right, not quick-and-dirty:
- Create or reuse a **single shared `AudioContext`** (never one per sound), and **resume it on the first user gesture** (click/keypress) — browsers block audio until then.
- Build a small reusable **sound system**: a `playSound('name')` function backed by a library of synthesized effects. Techniques to use:
  - **Tones** (coin, blip, UI): oscillator + a quick **gain envelope** (fast attack, short decay).
  - **Hits / explosions / whooshes**: short bursts of **filtered white noise**.
  - **Jumps / power-ups**: a **pitch sweep** (frequency ramp).
  - **Pickups / success**: a small **arpeggio** (a few rising notes).
  - **Failure / damage**: a **descending** tone.
- Keep each effect **short and punchy**, and **randomize the pitch slightly** on repeated plays so it never gets grating.
- Add a **mute toggle** (e.g. the **M** key) and keep master volume modest so it doesn't clip.
- Wire each sound to the correct game event without breaking gameplay.

**If I want background music**, also add a looping procedural track:
- Build it from a **simple chord progression + melody/arpeggio** on basic oscillators (square/triangle for chiptune, sine for soft), with light bass and optional noise percussion. **Pick a scale on purpose** to fit the mood (minor = tense, major/pentatonic = upbeat).
- Make it **loop seamlessly**, keep it **subtle and pleasant over long sessions**, reuse the same `AudioContext`, start it **only after a user gesture**, and **mix it under the SFX** so effects stay audible. The **M** key mutes everything.

After implementing: list which sound plays on which event (and how to start/stop music), tell me the mute key, and remind me to run it (with sound on), play it, and `/checkpoint` if I like it.
