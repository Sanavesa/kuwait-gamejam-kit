---
description: Make the game scale crisply to any screen + basic mobile/touch support
---
Make my game look sharp and play well on **any screen size**, without changing gameplay or feel.

Implement carefully:
- **Crisp scaling:** size the canvas to the window while keeping the game's **aspect ratio** (letterbox/pillarbox, never stretch). Handle **`devicePixelRatio`** so it isn't blurry on high-DPI screens; use `image-rendering: pixelated` for pixel art.
- **Fixed virtual resolution:** keep game logic in a fixed coordinate space and scale only the *rendering*, so physics and speeds don't change with window size.
- **Resize handling:** update on window resize / orientation change **without resetting** the game.
- **Fullscreen:** add an optional toggle (e.g. **F**).
- **Touch / mobile** (if it suits the game): map touch — tap, on-screen buttons, or drag — to the same actions as the keys, with large hit areas. Prevent page scroll/zoom/pinch on touch.
- **Keyboard in the iframe:** `preventDefault()` on the keys the game uses (especially **arrows and space**) so they drive the game instead of scrolling the itch page. Inside itch's iframe, **keyboard input doesn't reach the game until the player clicks it** — so make the first click/press grab focus (focus the canvas, or use a "click to start" gate) so a judge isn't met with a game that looks frozen.
- **itch.io iframe:** make sure it still works embedded in an iframe (the common jam target) — fit the frame, don't assume full window.

Don't change difficulty or feel. After implementing, tell me what changed, remind me to test resizing (and a phone if I can), then `/checkpoint`.
