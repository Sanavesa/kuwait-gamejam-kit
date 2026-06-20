# Game Jam Kit — the focused Claude Code plugin for beginners

A lean, beginner-first game-dev toolkit for Claude Code. It turns the whole jam — **idea → build → polish → ship** — into **9 one-word commands** and primes every session into "game-jam mode." No engine, no build tools, no clutter.

> **You only need 5 to start:** `/brainstorm` → `/new-game` → build with `/fix` + `/checkpoint` → `/juice` → `/submit`. The rest are there when you reach for them.
>
> 👉 **New here? Jump to the [Walkthrough](#walkthrough--your-first-game-start-to-finish) below** — a friendly start-to-finish guide.

---

## Walkthrough — your first game, start to finish
*Never used Claude Code? Follow this top to bottom and you'll ship a game. The one thing to understand: **you don't write code — you talk, Claude builds.** The rhythm never changes:*
> **type a command → Claude does it → you run & play the game → save a checkpoint → next.**

*(Install the kit first — see [Install](#install) below — then:)*

1. **Find an idea — `/brainstorm <the jam theme>`.** Claude cracks the theme into fresh angles, asks the feeling you want, then suggests small, finishable ideas and helps you pick one.
2. **Build the first playable version — `/new-game <your idea in one line>`.** Claude writes a complete `index.html`, tells you how to open it, writes a short `CLAUDE.md` "memory" so it remembers your game across sessions, and saves your first checkpoint. **Open it in your browser and play. 🎉**
3. **Its memory stays current on its own.** Your game already has a `CLAUDE.md` from step 2, and Claude keeps it in sync as the game changes — you don't maintain it. (You can still nudge it any time: *"update the game brief: the theme is underwater."*)
4. **The build loop — make it yours (no command needed).** Adding features is just *talking*: ask in plain words (*"add a double jump"*, *"make the pipes spawn slower"*, *"add a score +1 per pipe"*). Claude keeps each change small, won't break what already works, and reminds you to play + checkpoint — that discipline is built into every session. Play after **every** change. Like it? `/checkpoint score works`. Broke it? `/fix the bird falls through the floor` or `/undo`.
5. **Make it feel & look good** (where the points are): `/juice` (shake, particles, pops) · `/sound` (SFX + music in code) · `/art` (cohesive look, or wire in an image). Run one at a time, play, `/checkpoint`. *(Need a title / pause / game-over screen? Just ask — Claude builds the whole game shell, with a saved high score, as proper states. Crisp scaling to any screen is already built in.)*
6. **Playtest it — with real humans.** Hand it to a friend and *say nothing* — watch where they get confused; that's your fix list. (You're the first playtester too: do the first 30 seconds make sense with no instructions?) Fix what you saw with `/fix` and `/juice`.
7. **Submit it — `/submit`.** One command does the whole submission: zips the game correctly for itch.io, drafts your full page text (premise, controls, credits) ready to paste, and prints the upload checklist. **Upload early, then keep improving and re-run it.**

> **Stuck?**
>
> | If… | Do this |
> |---|---|
> | **Blank screen / something's broken** | Press **F12** → **Console** tab → copy the red error → `/fix` and paste it (or drag in a screenshot). |
> | **A change made it worse** | `/undo`, then try again in a smaller step. |

---

## Commands (9)

**Ideate**
| Command | Does |
|---|---|
| `/brainstorm [theme]` | Cracks the jam theme (angles, clichés to dodge) **then** guides ideation with game-design theory (**MDA**) → one small, fun, finishable idea. |

**Build**
| Command | Does |
|---|---|
| `/new-game <idea>` | Scaffolds a playable single-file `index.html`, writes a `CLAUDE.md` game brief, sets up git, saves the first checkpoint. |
| `/checkpoint [name]` | Saves a git "save point" (auto-names it from what changed if you skip the name). |
| `/undo [name]` | Rolls back to the last (or a named) checkpoint. |
| `/fix <error/bug>` | Paste a console error or describe the bug; smallest fix, escalating to systematic debugging if needed. |

**Make it good**
| Command | Does |
|---|---|
| `/juice [moment]` | Game feel: screen shake, particles, pops, hit-pause, flashes. |
| `/sound [what]` | Generates sound effects **and** looping music **in code** (Web Audio) — no downloads. |
| `/art [what]` | Creates cohesive art with no artist (procedural/code-drawn, palette) **or wires in a file you added**. |

**Ship**
| Command | Does |
|---|---|
| `/submit` | One-stop submission: zips the game (`index.html` at root), writes your full itch.io page text (premise, controls, features, credits), and prints the upload checklist. |

> **Playtesting is a human job:** hand the game to someone and watch them play without helping. The kit builds and ships; *people* tell you what's fun.

---

## Install

### Core kit (recommended — two commands)
This folder is a Claude Code **marketplace**. The org publishes it as a public git repo (e.g. `Sanavesa/kuwait-gamejam-kit`); then anyone runs, inside Claude Code:
```
/plugin marketplace add Sanavesa/kuwait-gamejam-kit
/plugin install gamejam@kuwait-gamejam
```
Done — all 9 commands are live in every project.

### Offline / no-GitHub fallback
Copy `plugins/gamejam/commands/` into your game folder as `.claude/commands/`. Same commands. (A folder of command files is the original, rock-solid mechanism; the plugin just wraps it.)
