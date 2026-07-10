# 🚀 VOIDRUNNER

A polished browser-based space combat game — built entirely with **vanilla HTML, CSS, and JavaScript**. No frameworks, no engines, no external assets. Just one file.

**[▶ Play it live](https://hamedabdullahmachrur.github.io/voidrunner-game/)**

![No dependencies](https://img.shields.io/badge/dependencies-none-5ef1c4?style=flat-square)
![Vanilla JS](https://img.shields.io/badge/JavaScript-vanilla-7c6ff2?style=flat-square)
![Single file](https://img.shields.io/badge/build-single%20HTML%20file-ff5d73?style=flat-square)

---

## 🎮 About

VoidRunner is a dark, neon-lit arcade shooter. Pilot your ship through waves of enemy drones, interceptors, and turrets, collect coins and power-ups, chain kills for score multipliers, and take down a boss every third sector.

It's built as a single self-contained `index.html` file — everything (rendering, physics, audio, particles, UI) runs client-side with zero network requests and zero external libraries.

## ✨ Features

- **Canvas-rendered gameplay** at a smooth 60 FPS with delta-time movement
- **Synthesized audio** — every sound effect and the ambient music loop are generated live with the Web Audio API (no audio files)
- **Particle system** — explosions, thruster trails, sparks, floating damage text, coin bursts, all via a pooled particle system (no garbage collection stutter)
- **Camera shake & screen flash** on impacts and death
- **Combo system** with score multipliers
- **5 power-ups**: shield, rapid fire, spread shot, hull repair, energy refill
- **3 enemy types** with distinct movement AI (sine weave, dive-bomb, hover) plus a **boss battle** every 3 sectors with multiple attack patterns
- **Progressive difficulty** — enemies get faster, tougher, and more frequent as you advance
- **3 difficulty presets** (Easy / Normal / Hard)
- **Full menu system** — animated main menu, how-to-play, settings, pause menu, game over, and victory screens
- **High score persistence** via `localStorage`
- **Responsive & touch-ready** — full keyboard controls on desktop, virtual joystick + fire button on mobile
- **Zero dependencies** — no React, no Phaser, no build tools, no CDN calls

## 🕹️ Controls

| Action | Desktop | Mobile |
|---|---|---|
| Move | `WASD` / Arrow keys | Left virtual joystick |
| Fire | `Space` | Right FIRE button |
| Pause | `Esc` or pause icon | Pause icon |

## 🛠️ Tech Stack

- **HTML5 Canvas** for all game rendering
- **Vanilla JavaScript** (ES6 classes) for game logic
- **Web Audio API** for all sound (oscillators + filtered noise, no audio files)
- **CSS3** for UI, menus, gradients, and glow effects
- **localStorage** for high score and settings persistence

No package.json. No node_modules. No build step. Open the file and it runs.

## 📁 Project Structure

```
voidrunner-game/
└── index.html   ← everything: markup, styles, and game engine in one file
```

## 🚀 Running Locally

Just open `index.html` in any modern browser:

```bash
git clone https://github.com/hamedabdullahmachrur/voidrunner-game.git
cd voidrunner-game
open index.html   # or double-click it
```

No server, no install, no build required.

## 🌐 Deployment

This project is deployed via **GitHub Pages** directly from this repository — any push to `main` updates the live version automatically.

To deploy your own fork:
1. Push this repo to your GitHub account
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch**, branch `main`, folder `/ (root)`
4. Your game will be live at `https://yourusername.github.io/voidrunner-game/`

## 🧩 Architecture Overview

The game logic is organized into clear sections inside `index.html`:

- **`AudioEngine`** — synthesizes all SFX and music in real time via Web Audio oscillators and noise buffers
- **`ParticlePool` / `FX`** — object-pooled particle system for explosions, trails, and floating text with no per-frame allocation
- **Entity classes** — `Player`, `Enemy`, `Boss`, `Bullet`, `Coin`, `PowerUp`, each owning their own `update()` / `render()`
- **`InputManager`** — unifies keyboard input and a custom touch-based virtual joystick
- **`Starfield`** — parallax background across 3 depth layers
- **`Game`** — the central state machine (menu → playing → paused → game over / victory) that drives the `requestAnimationFrame` loop, spawning, collisions, HUD updates, camera shake/flash, and `localStorage` persistence

## 📜 License

Free to use, modify, and build on.

---

Built as a demonstration of what's achievable in browser games with nothing but vanilla web technologies.