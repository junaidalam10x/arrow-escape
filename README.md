<div align="center">

<img src="icon-512.png" alt="Arrow Escape icon" width="120" height="120">

# Arrow Escape

**Slide every arrow out of the maze — before you run out of hearts.**

A calm-but-tricky arrow puzzle for your phone. Play solo, race the clock, or team up with a friend on one shared board.

[![Play](https://img.shields.io/badge/▶_Play_now-6f5cf0?style=for-the-badge)](https://junaidalam10x.github.io/arrow-escape/)
![Version](https://img.shields.io/badge/version-1.58.5-6f5cf0?style=flat-square)
![PWA](https://img.shields.io/badge/PWA-installable-1d1f2e?style=flat-square)
![Offline](https://img.shields.io/badge/works-offline-1d1f2e?style=flat-square)
![Co-op](https://img.shields.io/badge/online-2--player_co--op-1d1f2e?style=flat-square)
![No dependencies](https://img.shields.io/badge/dependencies-none-1d1f2e?style=flat-square)

</div>

---

## Table of contents

1. [What is Arrow Escape?](#what-is-arrow-escape)
2. [How to play](#how-to-play)
3. [Game modes](#game-modes)
4. [Difficulty](#difficulty)
5. [Online co-op](#online-co-op)
6. [Collection and rewards](#collection-and-rewards)
7. [Features](#features)
8. [Install on your phone](#install-on-your-phone)
9. [Project structure](#project-structure)
10. [Tech overview](#tech-overview)
11. [Run it locally](#run-it-locally)
12. [Releasing an update](#releasing-an-update)
13. [Credits](#credits)

---

## What is Arrow Escape?

Every board is a maze of snaking arrows packed inside a shape — a moon, a heart, a crown, a rocket and more. Each arrow points in one direction. Tap it and it slides out along its path — **but only if nothing is in its way.** Tap a blocked arrow and it turns red and costs you a heart.

Clear the whole board and the shape lights up in a rainbow ripple, bursts into sparkles and leaves a glowing outline behind.

It is a single, dependency-free HTML5 canvas game: fast to load, tiny to ship, and playable with one thumb.

## How to play

1. **Tap an arrow** to slide it out of the board.
2. If its way is **clear**, it leaves. If another arrow blocks it, it **turns red** and you lose a heart (❤️ × 3).
3. A red arrow leaves on its own as soon as its way clears.
4. **Clear every arrow** to win. Lose all hearts (or run out of time in a Challenge) and the round is over.
5. **Pinch** to zoom, **drag** to move around big boards. Use the 💡 hint if you are stuck and ↻ to start again.

The very first time you play, a short preview shows you how to move your first arrow.

### The magical arrow (Nightmare)

Every Nightmare board hides one glowing **golden arrow**. When its path is clear and you tap it, it leaves and **takes its nearest neighbours with it** — a handy shortcut on a huge board. If its way is blocked it behaves like any other arrow.

## Game modes

| Mode | What it is |
| --- | --- |
| **Levels** | An endless ladder. Every level is the same board for everybody, with a fixed difficulty. Level 1 is always Easy; Nightmare never appears before level 16. |
| **Challenge** | Timed levels with a countdown that tightens as you climb. Run out of time and the round ends. |
| **Quick play** | Pick a difficulty and play a fresh random board. |
| **Online co-op** | Two phones, one shared board, one shared pool of hearts. |
| **Offline** | No connection? Solo play always works. |

## Difficulty

| Level | Board size | Typical arrows | What changes |
| --- | --- | --- | --- |
| Easy | 14 × 14 | ~33 | Short, friendly arrows |
| Medium | 18 × 18 | ~54 | Longer paths, more crossings |
| Hard | 28 × 28 | ~135 | Dense boards, occasional long arrows covering 5–10% of the board |
| Nightmare | 38 × 38 | ~337 | Huge boards, long arrows, and the golden magical arrow |

Challenge time per arrow: Easy 0.85 s · Medium 0.75 s · Hard 0.65 s · Nightmare 0.55 s (tightens further with each level).

## Online co-op

Play on **two phones at the same time** on one board.

- One player taps **Play with friend** and becomes the **host**; a **room code** is shown.
- The friend enters the code to join. The code can be **copied** with one tap or **shared** straight from the app.
- Moves appear on both phones in real time. A free arrow is written directly by whoever taps it, so it shows up instantly; blocked taps are judged by the host so both phones always agree.
- Hearts and score are shared. You win and lose together.
- No internet? The lobby tells you so and offers **Play offline** instead.

> Both phones must be on the **same version** of the app when playing online.

## Collection and rewards

Winning games earns hand-drawn, **animated collectibles** — floating, swaying, flickering little creatures, planets and trinkets.

- **Lucky drops:** roughly one win in three can drop a random item. Rarer items drop less often.
- **Goal badges:** special items unlock only by completing goals. Locked items show the goal and a **progress bar**. Examples:
  - Win 5 games · Win 100 games
  - Play 3 days in a row
  - Win 10 games in a row
  - Win a game without losing a heart
  - Clear level 10 / 25 / 30 / 40
  - Clear Challenge level 3 / 5 / 15
  - Clear 500 / 3000 arrows
  - Win an online co-op game

## Features

- 🧩 **Shaped boards** — 40+ silhouettes (moon, heart, crown, rocket, cat, mushroom, ghost…), each procedurally filled with arrows.
- 🌱 **Seeded generation** — deterministic boards, so every player gets the same level and both co-op phones build the identical board.
- ✨ **Win show** — rainbow ripple, sparkle burst and a smooth glowing outline of the shape.
- 🟣 **Leaving-arrow trail** — the dots along an arrow's path light up as it slides away.
- 👥 **Online co-op** over Firebase Realtime Database, with room code, copy and share.
- ⏱️ **Challenge mode** with a shrinking clock.
- 🏆 **Animated collection** with goal-based unlocks and progress bars.
- 🔥 **Daily streaks** and stats (wins, streak, arrows cleared, perfect wins).
- 🌗 **Dark and light themes.**
- 🔊 **Sound and haptics**, including a countdown tick.
- 📴 **Offline-first** — a service worker caches the whole game.
- 📲 **Installable** to the home screen, full-screen, portrait.
- 🪶 **No frameworks, no build step, no tracking.**

## Install on your phone

**Android (Chrome)**

1. Open <https://junaidalam10x.github.io/arrow-escape/>
2. Tap **⋮ → Install app** (or **Add to Home screen**).

**iPhone (Safari)**

1. Open the link above in Safari.
2. Tap **Share → Add to Home Screen**.

Open the app once online so it can cache itself — after that it works offline.

## Project structure

```
arrow-escape/
├── index.html            # the entire game: HTML, CSS and JavaScript
├── sw.js                 # service worker (offline cache)
├── manifest.json         # PWA manifest (name, icons, fullscreen, portrait)
├── firebase-config.js    # Firebase project settings for online co-op
├── icon.svg
├── icon-192.png
├── icon-512.png
├── icon-maskable-512.png
├── apple-touch-icon.png
└── README.md
```

## Tech overview

| Area | Details |
| --- | --- |
| Rendering | HTML5 `<canvas>`, device-pixel-ratio aware, pinch-zoom and pan |
| Boards | `mulberry32` seeded RNG → shape mask → dense arrow generator (`genDense`) with per-difficulty tiers |
| Rules | An arrow can leave when every cell along its straight exit ray is empty |
| Online | Firebase Realtime Database (`rooms/{code}/meta`, `players`, `games/{n}/events`), host referees blocked taps |
| Storage | `localStorage` for settings, level progress, collection and stats |
| Offline | Service worker with versioned cache (`arrow-escape-vNN`) |
| Effects | Canvas particles, ripple/rainbow win show, animated SVG collectibles |

## Run it locally

No install or build is needed.

```bash
git clone https://github.com/junaidalam10x/arrow-escape.git
cd arrow-escape
python3 -m http.server 8080
```

Then open <http://localhost:8080>. A local server (not `file://`) is needed for the service worker.

For online co-op, put your own Firebase Realtime Database settings in `firebase-config.js`.

## Releasing an update

Every release must change **two** things, otherwise phones keep showing the old cached game:

1. In `index.html`, bump `const VERSION = '…'`.
2. In `sw.js`, bump the cache name, e.g. `arrow-escape-v139` → `arrow-escape-v140`.

Upload both files, then open the app **twice** (the first open installs the update, the second shows it).
If the change touches online logic or board generation, **both phones** need the new version.

## Credits

Designed and built by **Junaid Alam**.
Hosted on GitHub Pages · Online play powered by Firebase Realtime Database.

<div align="center">

Made with care for quick, satisfying puzzle breaks. 🏹

</div>
