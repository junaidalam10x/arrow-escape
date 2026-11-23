<div align="center">

<img src="icon-512.png" alt="Arrow Escape icon" width="120" height="120">

# Arrow Escape

**Slide every arrow out of the maze before you run out of hearts.**

A calm-but-tricky arrow puzzle for your phone.
Play solo, race the clock, or team up with a friend on one shared board.

[![Play now](https://img.shields.io/badge/▶_Play_now-6f5cf0?style=for-the-badge)](https://junaidalam10x.github.io/arrow-escape/)

![Version](https://img.shields.io/badge/version-1.58.7-6f5cf0?style=flat-square)
![PWA](https://img.shields.io/badge/PWA-installable-1d1f2e?style=flat-square)
![Offline](https://img.shields.io/badge/works-offline-1d1f2e?style=flat-square)
![Co-op](https://img.shields.io/badge/online-2--player_co--op-1d1f2e?style=flat-square)
![Dependencies](https://img.shields.io/badge/dependencies-none-1d1f2e?style=flat-square)

[**Play**](#-play) · [**Modes**](#-game-modes) · [**Co-op**](#-online-co-op) · [**Collection**](#-collection) · [**Install**](#-install) · [**Develop**](#-for-developers)

</div>

---

## At a glance

| | |
| --- | --- |
| **Genre** | Arrow-escape puzzle |
| **Platforms** | Any phone browser, installable as an app (Android and iPhone) |
| **Players** | 1 (solo) or 2 (online co-op) |
| **Works offline** | Yes, solo play |
| **Difficulties** | Easy · Medium · Hard · Nightmare |
| **Tech** | One HTML5 canvas file, no frameworks, no build step |

---

# 🎮 Play

## What is it?

Every board is a maze of snaking arrows packed inside a shape: a moon, a heart, a crown, a rocket and more. Tap an arrow and it slides out along its path, **but only if nothing is in its way.** Tap a blocked arrow and it turns red and costs you a heart.

Clear the whole board and the shape lights up in a rainbow ripple, bursts into sparkles and leaves a glowing outline behind.

## How to play

1. **Tap an arrow** to slide it out of the board.
2. **Clear way:** it leaves. **Blocked:** it turns red and you lose a heart (you have 3).
3. A red arrow leaves on its own as soon as its way clears.
4. **Clear every arrow to win.** Lose all hearts, or run out of time in a Challenge, and the round is over.

**Controls**

| Action | Gesture or button |
| --- | --- |
| Move an arrow | Tap it |
| Zoom | Pinch |
| Look around a big board | Drag |
| Get a hint | 💡 |
| Start the board again | ↻ |

The first time you play, a short preview shows you how to move your first arrow.

## Special arrows

**The magical arrow (Nightmare only).** Every Nightmare board hides one glowing golden arrow. When its way is clear and you tap it, it leaves and takes along its nearest neighbours that can also leave. If its way is blocked, it behaves like any other arrow.

**Long arrows (Hard and Nightmare).** Each board has one or two long arrows that cover 5–10% of the board by themselves (normal arrows cover 1–2%). Their heads usually point outward.

## 🕹 Game modes

| Mode | What it is |
| --- | --- |
| **Levels** | An endless ladder. Every level is the same board for everybody, with a fixed difficulty. Level 1 is always Easy; Nightmare never appears before level 16. |
| **Challenge** | Timed levels with a countdown that tightens as you climb. |
| **Quick play** | Pick a difficulty and play a fresh random board. |
| **Online co-op** | Two phones, one shared board, one shared pool of hearts. |

## Difficulty

| Level | Board | Typical arrows | What to expect | Challenge time per arrow |
| --- | --- | --- | --- | --- |
| Easy | 14 × 14 | ~33 | Short, friendly arrows | 0.85 s |
| Medium | 18 × 18 | ~54 | Longer paths, more crossings | 0.75 s |
| Hard | 28 × 28 | ~135 | Dense boards and long arrows | 0.65 s |
| Nightmare | 38 × 38 | ~337 | Huge boards, long arrows and the magical arrow | 0.55 s |

Challenge time tightens a little with every level.

## 👥 Online co-op

Play on two phones at the same time on one board.

1. One player taps **Play with friend** and becomes the **host**. A **room code** appears.
2. The friend enters the code to join. The code can be **copied** with one tap or **shared** straight from the app.
3. Moves appear on both phones in real time. Hearts and score are shared, so you win and lose together.
4. No internet? The lobby says so and offers **Play offline**.

> Both phones must be on the **same version** of the app.

## 🏆 Collection

Winning earns hand-drawn, **animated collectibles**: floating, swaying, flickering creatures, planets and trinkets.

| Way to earn | How it works |
| --- | --- |
| **Lucky drops** | Roughly one win in three drops a random item. Rarer items drop less often. |
| **Goal badges** | Special items unlock only by completing a goal. Locked items show the goal and a progress bar. |

Example goals: win 5 or 100 games · play 3 days in a row · win 10 games in a row · win without losing a heart · clear level 10, 25, 30 or 40 · clear Challenge level 3, 5 or 15 · clear 500 or 3000 arrows · win an online co-op game.

## ✨ Features

- 🧩 40+ shaped boards, each filled with arrows by a generator
- 🌱 Seeded boards: the same level for every player, identical on both co-op phones
- ✨ Win show: rainbow ripple, sparkle burst and a smooth glowing outline
- 🟣 Leaving-arrow trail along the dots of its path
- ⏱️ Challenge mode with a shrinking clock
- 🔥 Daily streaks and stats
- 🌗 Dark and light themes
- 🔊 Sound and haptics
- 📴 Offline-first with a service worker
- 🪶 No frameworks, no build step, no tracking

---

# 📲 Install

| Phone | Steps |
| --- | --- |
| **Android (Chrome)** | Open <https://junaidalam10x.github.io/arrow-escape/> → **⋮** → **Install app** (or **Add to Home screen**) |
| **iPhone (Safari)** | Open the link → **Share** → **Add to Home Screen** |

Open the app once online so it can save itself. After that it works offline.

> The home-screen name is set when you install. To pick up a new name or icon, remove the old icon and install again.

---

# 🛠 For developers

## Project structure

```
arrow-escape/
├── index.html            the whole game: HTML, CSS and JavaScript
├── sw.js                 service worker (offline cache)
├── manifest.json         app manifest: name, icons, fullscreen, portrait
├── firebase-config.js    Firebase settings for online co-op
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
| Boards | Seeded random numbers → shape mask → dense arrow generator, tuned per difficulty |
| Rules | An arrow leaves when every cell along its straight exit line is empty |
| Online | Firebase Realtime Database; the host referees blocked taps |
| Storage | `localStorage` for settings, level progress, collection and stats |
| Offline | Service worker with a versioned cache (`arrow-escape-vNN`) |
| Effects | Canvas particles, ripple and rainbow win show, animated SVG collectibles |

## Run it locally

```bash
git clone https://github.com/junaidalam10x/arrow-escape.git
cd arrow-escape
python3 -m http.server 8080
```

Open <http://localhost:8080>. Use a local server rather than `file://`, so the service worker can run.
For online co-op, put your own Firebase Realtime Database settings in `firebase-config.js`.

## Releasing an update

Every release changes **two** things, otherwise phones keep the old cached game:

1. `index.html`: bump `const VERSION = '…'`
2. `sw.js`: bump the cache name, for example `arrow-escape-v141` → `arrow-escape-v142`

Upload both files, then open the app **twice**: the first open installs the update, the second shows it.
If the change touches online logic or board generation, both phones need the new version.

---

<div align="center">

Designed and built by **Junaid Alam**
Hosted on GitHub Pages · Online play by Firebase Realtime Database

Made for quick, satisfying puzzle breaks 🏹

</div>
