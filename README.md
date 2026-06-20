# Game Jam Kit

A beginner-friendly game-dev toolkit for Claude Code. It turns the whole jam (idea, build, polish, ship) into 9 one-word commands, and primes every session into "game-jam mode." No engine, no build tools, no clutter.

> **You only need 5 to start:** brainstorm an idea (`/brainstorm`), scaffold it (`/new-game`), build it in a loop with `/fix` and `/checkpoint`, add polish (`/juice`), and ship it (`/submit`). The rest are there when you reach for them.

## Contents
- [Install](#install): get set up in two commands
- [How to use it](#how-to-use-it): your first game, start to finish
- [Command reference](#command-reference): all 9 commands at a glance
- [Troubleshooting](#troubleshooting): when something breaks

---

## Install

### Core kit (recommended, two commands)
This folder is a Claude Code **marketplace**, published as a public git repo (`Sanavesa/kuwait-gamejam-kit`). Inside Claude Code, run:
```
/plugin marketplace add Sanavesa/kuwait-gamejam-kit
/plugin install gamejam@kuwait-gamejam
```
That's it. All 9 commands are live in every project. Next: [How to use it](#how-to-use-it).

### Offline / no-GitHub fallback
Copy `plugins/gamejam/commands/` into your game folder as `.claude/commands/`. Same commands. (A folder of command files is the original mechanism; the plugin just wraps it.)

---

## How to use it

Your first game, start to finish. Never used Claude Code? Follow this top to bottom and you'll ship a game. The one thing to understand: you don't write code, you talk and Claude builds. The rhythm never changes:

> Type a command, Claude does it, you run and play the game, save a checkpoint, repeat.

First [install the kit](#install), then:

1. **Find an idea: `/brainstorm <the jam theme>`.** Claude cracks the theme into fresh angles, asks what feeling you want, then suggests small, finishable ideas and helps you pick one.
2. **Build the first playable version: `/new-game <your idea in one line>`.** Claude writes a complete `index.html`, tells you how to open it, writes a short `CLAUDE.md` "memory" so it remembers your game across sessions, and saves your first checkpoint. Open it in your browser and play.
3. **Its memory stays current on its own.** Your game already has a `CLAUDE.md` from step 2, and Claude keeps it in sync as the game changes, so you don't have to maintain it. You can still nudge it any time: *"update the game brief: the theme is underwater."*
4. **The build loop (no command needed).** Adding features is just talking. Ask in plain words: *"add a double jump"*, *"make the pipes spawn slower"*, *"add a score +1 per pipe."* Claude keeps each change small, won't break what already works, and reminds you to play and checkpoint. Play after every change. Like it? `/checkpoint score works`. Broke it? `/fix the bird falls through the floor`, or `/undo`.
5. **Make it feel and look good** (this is where the points are): `/juice` for shake, particles, and pops; `/sound` for effects and music in code; `/art` for a cohesive look or to wire in an image. Run one at a time, play, then `/checkpoint`. Need a title, pause, or game-over screen? Just ask, and Claude builds the whole game shell with a saved high score. Crisp scaling to any screen is already built in.
6. **Playtest it with real people.** Hand it to a friend and say nothing. Watch where they get confused; that's your fix list. (You're the first playtester too: do the first 30 seconds make sense with no instructions?) Fix what you saw with `/fix` and `/juice`.
7. **Submit it: `/submit`.** One command does the whole submission. It zips the game correctly for itch.io, drafts your full page text (premise, controls, credits) ready to paste, and prints the upload checklist. Upload early, then keep improving and re-run it.

Stuck at any point? See [Troubleshooting](#troubleshooting).

---

## Command reference

**Ideate**
| Command | Does |
|---|---|
| `/brainstorm [theme]` | Cracks the jam theme (angles, clichés to dodge), then guides ideation with game-design theory (MDA) to land one small, fun, finishable idea. |

**Build**
| Command | Does |
|---|---|
| `/new-game <idea>` | Scaffolds a playable single-file `index.html`, writes a `CLAUDE.md` game brief, sets up git, and saves the first checkpoint. |
| `/checkpoint [name]` | Saves a git "save point" (auto-names it from what changed if you skip the name). |
| `/undo [name]` | Rolls back to the last checkpoint, or a named one. |
| `/fix <error/bug>` | Paste a console error or describe the bug. Makes the smallest fix, escalating to systematic debugging if needed. |

**Make it good**
| Command | Does |
|---|---|
| `/juice [moment]` | Game feel: screen shake, particles, pops, hit-pause, flashes. |
| `/sound [what]` | Generates sound effects and looping music in code (Web Audio), no downloads. |
| `/art [what]` | Creates cohesive art with no artist (procedural or code-drawn, with a palette), or wires in a file you added. |

**Ship**
| Command | Does |
|---|---|
| `/submit` | One-stop submission: zips the game (`index.html` at root), writes your full itch.io page text (premise, controls, features, credits), and prints the upload checklist. |

> **Playtesting is a human job.** Hand the game to someone and watch them play without helping. The kit builds and ships; people tell you what's fun.

---

## Troubleshooting

| If… | Do this |
|---|---|
| **Blank screen, or something's broken** | Press **F12**, open the **Console** tab, copy the red error, then run `/fix` and paste it (or drag in a screenshot). |
| **A change made it worse** | `/undo`, then try again in a smaller step. |

[Back to top](#game-jam-kit)
