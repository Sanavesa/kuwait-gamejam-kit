# Game Jam Kit

A beginner-friendly game-dev toolkit for Claude Code. It turns the whole jam (idea, build, polish, ship) into 4 one-word commands, and primes every session into "game-jam mode" where Claude also handles art, sound, polish, and bug-fixing for you as the game grows. No engine, no build tools, no clutter.

> **You only need 3 to start:** start a game (`/new-game`), where Claude brainstorms the idea with you and then builds it, then loop by just talking (ask for changes, paste any error to fix it) and checkpointing with `/save`, and ship it (`/submit`). Polish, art, sound, and bug-fixing just happen as you build, no command needed. The rest are there when you reach for them.

## Contents
- [Before you start](#before-you-start): brand new to Claude Code? Read this first
- [Install](#install): get set up in two commands
- [How to use it](#how-to-use-it): your first game, start to finish
- [Command reference](#command-reference): all 4 commands at a glance
- [Troubleshooting](#troubleshooting): when something breaks

---

## Before you start

Brand new to all of this? You need two things before the kit can help, and that's it:

1. **Install Claude Code** and open it (the desktop app or the terminal). This is the program you'll talk to; the game gets built inside it.
2. **Make a folder for your game** and open it as your project (e.g. a new `my-game` folder). Everything, your `index.html`, checkpoints, and submission, lives here. One folder per game.

You won't write any code or touch the command line beyond this. From here on you just type commands and talk. Next: [Install](#install) the kit.

---

## Install

### Core kit (recommended, two commands)
This folder is a Claude Code **marketplace**, published as a public GitHub repo (`Sanavesa/kuwait-gamejam-kit`). Inside Claude Code, run:
```
/plugin marketplace add Sanavesa/kuwait-gamejam-kit
/plugin install gamejam@kuwait-gamejam
```
That's it. All 4 commands are live in every project. Next: [How to use it](#how-to-use-it).

### Offline / no-GitHub fallback
Copy `plugins/gamejam/commands/` into your game folder as `.claude/commands/`. Same commands. (A folder of command files is the original mechanism; the plugin just wraps it.)

---

## How to use it

Your first game, start to finish. Never used Claude Code? Follow this top to bottom and you'll ship a game. The one thing to understand: you don't write code, you talk and Claude builds. The rhythm never changes:

> Type a command, Claude does it, you run and play the game, save a checkpoint, repeat.

First [install the kit](#install), then:

1. **Start a game: `/new-game <your idea, or the jam theme, in one line>`.** Claude first brainstorms with you (a few quick questions to shape the core mechanic, feeling, and how it fits the theme), then writes a complete `index.html`, writes a short `CLAUDE.md` "memory" so it remembers your game across sessions, and saves your first checkpoint. To play, just **open `index.html` in your browser** (double-click it).
2. **Its memory stays current on its own.** Your game already has a `CLAUDE.md` from step 1, and Claude keeps it in sync as the game changes, so you don't have to maintain it. You can still nudge it any time: *"update the game brief: the theme is underwater."*
3. **The build loop (no command needed).** Adding features is just talking. Ask in plain words: *"add a double jump"*, *"make the pipes spawn slower"*, *"add a score +1 per pipe."* Claude keeps each change small, won't break what already works, and reminds you to play and checkpoint. Play after every change by reopening `index.html` (if a change doesn't show up, hard-refresh with **Ctrl/Cmd+Shift+R**, you're seeing a cached old version). Like it? `/save score works`. Broke it? Just say what's wrong (*"the bird falls through the floor"*) or paste the console error and Claude fixes it, or `/undo`.
4. **Make it feel and look good** (this is where the points are): once the core loop is fun, **just ask for polish** (*"juice up scoring"*) or let Claude offer, and it shows a short menu of game-feel effects (shake, particles, pops, and more) for you to pick from. For **sound and art, just ask** (*"add a coin sound"*, *"give the player a ship sprite"*), and Claude generates audio (Web Audio) and art (code-drawn, cohesive palette) right in the game. Want to use **your own** file? Drop it in the **`assets/` folder** (created for you with the game) and reference it as `@assets/player.png` when you ask, and Claude wires it in. All of this is on by default every session, no command needed. Run one thing at a time, play, then `/save`. Need a title, pause, or game-over screen? Just ask, and Claude builds the whole game shell with a saved high score. Crisp scaling to any screen is already built in.
5. **Playtest it with real people.** Hand it to a friend and say nothing. Watch where they get confused; that's your fix list. (You're the first playtester too: do the first 30 seconds make sense with no instructions?) Fix what you saw by just describing it (or pasting the error), and ask for polish where it'll help.
6. **Submit it: `/submit`.** One command does the whole submission. It zips the game correctly for itch.io, drafts your full page text (premise, controls, credits) ready to paste, and prints the upload checklist. Upload early, then keep improving and re-run it.

Stuck at any point? See [Troubleshooting](#troubleshooting).

---

## Command reference

**Build**
| Command | Does |
|---|---|
| `/new-game <idea/theme>` | Brainstorms the idea with you (core mechanic, feeling, theme fit), then scaffolds a playable single-file `index.html`, writes a `CLAUDE.md` game brief, sets up your save points, and saves the first checkpoint. |
| `/save [label]` | Saves a checkpoint as an auto-incrementing version (`v1`, `v2`, ...) plus your optional label. |
| `/undo [version/label]` | Rolls back to a checkpoint by version (e.g. `v3`), by label, or your last save if omitted, after confirming with you first. |

**Make it good & fix it** (no command needed)

> **Playing your game.** Just **open `index.html` in your browser** (double-click it), no setup, no server. After a change, refresh the page; if it still looks the same, hard-refresh with **Ctrl/Cmd+Shift+R** (you're seeing a cached old version).

> **Art, sound, and polish need no command.** Just ask in plain words (*"add a coin sound"*, *"give the player a ship sprite"*, *"juice up scoring"*) and Claude generates audio (Web Audio) and art (code-drawn, cohesive palette) right in the game and offers a menu of game-feel effects (shake, particles, pops, hit-pause, flashes) to pick from. To use **your own** asset, drop it in the **`assets/` folder** and reference it as `@assets/name.png` when you ask. This is on by default in every session.

> **Bug-fixing needs no command either.** Paste a browser console error or just describe what's wrong (*"the bird falls through the floor"*) and Claude finds the root cause, makes the smallest fix, and escalates to systematic debugging if the bug is stubborn. No error to copy? Press **F12 → Console tab → copy the red text**, or drag in a screenshot.

**Ship**
| Command | Does |
|---|---|
| `/submit` | One-stop submission: zips the game (`index.html` at root), writes your full itch.io page text (premise, controls, features, credits), and prints the upload checklist. |

> **Playtesting is a human job.** Hand the game to someone and watch them play without helping. The kit builds and ships; people tell you what's fun.

---

## Troubleshooting

| If… | Do this |
|---|---|
| **My change didn't show up** | Hard-refresh the browser: **Ctrl/Cmd + Shift + R**. You're almost always looking at a cached old version. |
| **Blank screen, or something's broken** | Press **F12**, open the **Console** tab, copy the red error, then paste it into the chat (or drag in a screenshot) and Claude fixes it. |
| **The keys do nothing** | Click the game once so it has focus, then try again. If it still won't respond, tell Claude, it makes the game grab keyboard focus automatically. |
| **No sound** | Browsers block audio until you interact: click or press a key once to start. Press **M** to toggle mute. |
| **Not sure how to open the game** | Find `index.html` in your game folder and double-click it; it opens in your browser. That's all it takes. |
| **A change made it worse** | `/undo`, then try again in a smaller step. |

[Back to top](#game-jam-kit)
