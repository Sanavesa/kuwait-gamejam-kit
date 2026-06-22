---
description: Add game art, generated in code or from your files
argument-hint: (optional) what you need, e.g. "a player ship" or "use player.png as the player"
---
Be my **art director**. I have no artist and little time. Two goals: the game must look **intentional** (not like a programmer placeholder), and I must **never be blocked** waiting on art.

**If I already dropped art files in the folder** (named in "$ARGUMENTS", e.g. *"use player.png as the player"*), just wire them in: load each by its real filename in place of the matching shape/sprite, scale it sensibly, keep it crisp, make sure it still loads when the game runs, bundle the files with the game so nothing has to download at play time, and remind me to **credit** them. Handle whatever I have — single sprites, a spritesheet, or a background image. Otherwise, create art:

If "$ARGUMENTS" says what I need, use it; otherwise ask briefly what elements + vibe I want. Then **recommend** one approach (default to #1 for a jam) and do it:

1. **Procedural / code-drawn art (fastest — recommended):** draw sprites and scenery directly with canvas/SVG — characters, enemies, particles, and backgrounds (gradients, starfields, parallax layers, simple tiles). Zero downloads, stays self-contained.
2. **Curated free assets:** if I want real sprites, point me to Kenney (kenney.nl) / OpenGameArt (opengameart.org), help me pick a **cohesive set**, then wire them in.
3. **AI-generated:** if I want custom art, give me the exact prompt to use in an image tool (and how to get it transparent/cropped in Photopea), then wire it in.

Whatever we pick, apply real art direction:
- Choose a **cohesive, limited palette** (suggest a specific 4–6 colour palette) and a consistent **shape language / line weight**, and apply it to **every** element — consistency reads as "polished" far more than detail does.
- Render **crisply** (no blurry stretching; `image-rendering: pixelated` for pixel art) and **cheaply** (don't tank the frame rate).
- **Generate placeholder art now**, even if I'll replace it later — momentum over perfection.
- If we use any third-party or AI art, remind me to add it to my **credits list**.

Then show me the result and ask if I want to iterate on the look. Remind me to `/checkpoint`.
