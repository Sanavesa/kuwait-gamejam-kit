# Game Jam Kit — the focused Claude Code plugin for beginners

A lean, beginner-first game-dev toolkit for Claude Code. It turns the whole jam — **idea → build → polish → ship** — into **10 one-word commands** and primes every session into "game-jam mode." No engine, no build tools, no clutter.

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
3. **Keep its memory current.** Your game already has a `CLAUDE.md` from step 2 — whenever it changes a lot, just say *"update the game brief: the theme is underwater"* so Claude stays in sync.
4. **The build loop — make it yours (no command needed).** Adding features is just *talking*: ask in plain words (*"add a double jump"*, *"make the pipes spawn slower"*, *"add a score +1 per pipe"*). Claude keeps each change small, won't break what already works, and reminds you to play + checkpoint — that discipline is built into every session. Play after **every** change. Like it? `/checkpoint score works`. Broke it? `/fix the bird falls through the floor` or `/undo`.
5. **Make it feel & look good** (where the points are): `/juice` (shake, particles, pops) · `/sound` (SFX + music in code) · `/art` (cohesive look, or wire in an image) · `/menu` (title, pause, game over). Run one at a time, play, `/checkpoint`. *(Crisp scaling to any screen is already built in — ask if you also want touch controls or fullscreen.)*
6. **Playtest it — with real humans.** Hand it to a friend and *say nothing* — watch where they get confused; that's your fix list. (You're the first playtester too: do the first 30 seconds make sense with no instructions?) Fix what you saw with `/fix` and `/juice`.
7. **Submit it — `/submit`.** One command does the whole submission: zips the game correctly for itch.io, drafts your full page text (premise, controls, credits) ready to paste, and prints the upload checklist. **Upload early, then keep improving and re-run it.**

> **Stuck?** Blank screen → **F12** → Console → copy the red error → `/fix` (paste it), or drag in a screenshot. A change made it worse → `/undo`, then a smaller step. Still stuck after a few minutes → raise your hand.

---

## Commands (10)

**Ideate**
| Command | Does |
|---|---|
| `/brainstorm [theme]` | Cracks the jam theme (angles, clichés to dodge) **then** guides ideation with game-design theory (**MDA**) → one small, fun, finishable idea. |

**Build**
| Command | Does |
|---|---|
| `/new-game <idea>` | Scaffolds a playable single-file `index.html`, writes a `CLAUDE.md` game brief, sets up git, saves the first checkpoint. |
| `/checkpoint <name>` | Saves a git "save point." |
| `/undo [name]` | Rolls back to the last (or a named) checkpoint. |
| `/fix <error/bug>` | Paste a console error or describe the bug; smallest fix, escalating to systematic debugging if needed. |

**Make it good**
| Command | Does |
|---|---|
| `/juice [moment]` | Game feel: screen shake, particles, pops, hit-pause, flashes. |
| `/sound [what]` | Generates sound effects **and** looping music **in code** (Web Audio) — no downloads. |
| `/art [what]` | Creates cohesive art with no artist (procedural/code-drawn, palette) **or wires in a file you added**. |
| `/menu [name]` | Full game flow: title, how-to-play, pause, game over + high score, restart. |

**Ship**
| Command | Does |
|---|---|
| `/submit` | One-stop submission: zips the game (`index.html` at root), writes your full itch.io page text (premise, controls, features, credits), and prints the upload checklist. |

*(Crisp scaling, high-DPI sharpness, and itch-iframe safety are built into `/new-game` and maintained as you build — no separate command needed. Ask any time to add touch controls or fullscreen.)*

> **Playtesting is a human job:** hand the game to someone and watch them play without helping. The kit builds and ships; *people* tell you what's fun.

## Session primer (hook)
A `SessionStart` hook quietly keeps Claude in "game-jam mode" — small steps, playtest often, suggest the right command, default to a single self-contained file. You do nothing; it just stays helpful.

---

## Install

### Core kit (recommended — two commands)
This folder is a Claude Code **marketplace**. The org publishes it as a public git repo (e.g. `Sanavesa/kuwait-gamejam-kit`); then anyone runs, inside Claude Code:
```
/plugin marketplace add Sanavesa/kuwait-gamejam-kit
/plugin install gamejam@kuwait-gamejam
```
Done — all 10 commands + the primer are live in every project.

### Offline / no-GitHub fallback
Copy `plugins/gamejam/commands/` into your game folder as `.claude/commands/`. Same commands. (A folder of command files is the original, rock-solid mechanism; the plugin just wraps it.)

---

## Design notes

**Kept lean on purpose.** Each command is a *distinct* jam task — no near-variants, and **one mental model: commands** (no separate subagents to learn; debug/art expertise lives in `/fix` and `/art`).

**Why a custom kit?** (Researched June 2026.) Nothing existing fits "pure beginners + single-file browser games + a 72h jam." The official marketplace has no game-dev plugins; community Phaser/engine plugins add npm + build steps that break "just open `index.html`." A small tailored kit is exactly Anthropic's recommended use of commands/skills.

**Graduating after the jam:** Phaser (2D) via the community `game-creator` / `phaser4-gamedev` plugins · Three.js/Babylon.js (3D) · engines: Godot → Unity / Unreal.

## What's in here (for maintainers)
```
kuwait-gamejam-kit/
├── README.md                             # this file (install + walkthrough)
├── LICENSE                               # MIT
├── .claude-plugin/
│   └── marketplace.json              # catalog: lists "gamejam"
└── plugins/
    └── gamejam/                       # the core plugin
        ├── .claude-plugin/plugin.json
        ├── commands/                  # 10 slash commands (auto-discovered)
        ├── hooks/hooks.json           # SessionStart "game-jam mode" primer
        └── templates/CLAUDE.md        # reference game-brief (/new-game writes this)
```
Each command is plain Markdown with YAML frontmatter — the documented Claude Code format. Edit a file to change behavior; bump `version` in the manifests to ship an update.
