# 🌱🍳 HarvestCrosing

> A cozy farming & restaurant game for the browser — a love-letter fusion of **Animal Crossing** (warm, characterful, collection-driven, no pressure) and **Story of Seasons** (the satisfying ritual of farming, ranching, cooking, tools, and seasons).

Built with **Three.js (WebGL)**, primitive geometry only (no external 3D models), and designed **mobile-first** with a heavily polished one-finger control scheme. Everything lives in a single self-contained `index.html` — no build step, no backend. Progress is saved to `localStorage`.

---

## ✨ Design pillars

1. **No fail-state.** No losing, no dead animals, no rotten crops. The worst outcome is "wait a little longer."
2. **Calming daily rituals, not a stressful time-sink.** Energy is a gentle rhythm, never a hard wall.
3. **NPCs with names and small personalities**, not anonymous "customer spawns."
4. **Story-of-Seasons depth** (tool upgrades, locked recipes, seasons) that stays optional and quick to reach — never grindy.
5. **Animal-Crossing collection & customization joy** (notebook, character looks, farm naming, land expansion).
6. **Genuinely smooth one-finger mobile controls** — the most polished system in the game.

---

## 🎮 Features

- **Polished touch controls** — dynamic virtual joystick (dead zone, clamp radius, analog speed), robust tap-vs-drag disambiguation, single-touch lock, camera-relative movement, live raycast highlight on touchmove, oversized hitboxes, auto-walk-to-interact, and haptics with graceful fallback.
- **Isometric smooth-follow camera** (45°, no OrbitControls) with subtle look-ahead.
- **Full day/season/weather cycle** — gradual sky/fog/light color transitions (morning → midday → golden hour → dusk → night with stars & fireflies), 4 seasons, daily weather (rain auto-waters crops), and a sleep-to-advance-day mechanic.
- 🌾 **Farming** — till, plant, water, harvest; seasonal seeds; a Level-2 watering can that waters a 3×3 at once.
- 🐮 **Ranching** — cow, chicken, sheep with mood; feed and pet (with heart particles); products drop when happy.
- 🍳 **Cooking** — 4 recipes with gradual unlocks and a recipe book (locked recipes shown as silhouettes).
- 🛒 **Economy** — souvenir shop, a **shipping bin** (auto-sells the next morning), and restaurant customers (same NPC system, with reactions and tips).
- 👥 **Villagers** — named NPCs with friendship hearts, rotating dialogue, small requests, and an occasional special-visitor event.
- 📖 **Collection & progression** — notebook checklist, milestone confetti, land/coop expansion, character customization, and a nameable farm sign.
- 🔊 **Juice & audio** — Web Audio generated ambient music + layered SFX, squash-stretch tweens, particle bursts, and floating popups.
- 💾 **Versioned save system** — debounced autosave + save-on-sleep, with a graceful in-memory fallback if `localStorage` is unavailable.

---

## 🚀 Run it

No build needed. Either:

- Open `index.html` directly in a modern browser, **or**
- Serve the folder (recommended for mobile testing):

```bash
# any static server works
npx serve .
# or
python3 -m http.server 8000
```

Then open it on your phone. The game is **portrait-locked** and will prompt you to rotate if held in landscape. Three.js is loaded from a CDN via an import map, so an internet connection is needed on first load.

---

## 🧱 Tech notes

- Single-file architecture with clear namespaced modules: `Util`, `Audio`, `GameState`, `SaveManager`, `SceneSetup`, `DayCycle`, `Builders`, `World`, `Input`, gameplay `Systems`, `UIManager`, and `Game`.
- `MeshStandardMaterial` with `flatShading`, `InstancedMesh` for repeated props, capped pixel ratio, and `clock.getDelta()` everywhere for frame-rate-independent timing — targeting **>30fps** on mid-range phones.

## 🗺️ Roadmap (`// TODO: v2`)

- Render the second 3×3 plot block when "expand land" is purchased (logic & coin-sink already work).
- Home interior decoration and animal naming.

---

*Philosophy: "deeper than Animal Crossing, more relaxed than Story of Seasons." Every extra system stays optional, quick, and never punishing.*
