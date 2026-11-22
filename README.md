# Neon Coast 3D — Suncrest Bay

An open-world 3D driving & heist game that runs entirely in the browser.
**One single HTML file. No build step. No server code.** Open it, host it anywhere static, and it plays.

Live demo: https://neon-coast-3d.pages.dev

---

## What the game includes

- **10-level campaign** — bank deposits, supercar hijack, outfit-swap escapes, boat smuggling runs, courier deliveries, police takedowns and a final $12,000 score, ending in free-roam mode where checkpoints keep paying.
- **Open world city** — a full road network with painted markings and crosswalks, 100+ buildings with lit windows, rooftop props, shopfront signs and billboards, streetlights, a beach with palms, docks and an ocean.
- **Living traffic** — ambient cars driving block loops with headlights, wandering NPC cars you can steal, walking pedestrians.
- **Police pursuit system** — wanted stars (1–5), chase AI with a fair "bust meter", takedowns, escape timers.
- **Garage & economy** — earn cash, deposit it at ATMs, buy and customise cars (multiple models including exotics and speedboats), fuel and nitro systems, stunt ramps with air control.
- **Co-op multiplayer** — peer-to-peer room codes (PeerJS): share a link/code and a second player appears in your world, in their own car.
- **Mobile ready** — on-screen touch controls, plus a **GFX HIGH/LOW toggle** (shadows/resolution) so it stays smooth on weak devices.
- **Sound** — a built-in synthwave radio and sound effects generated with WebAudio. No audio files.
- **Persistence** — progress, bank and garage are saved in the browser (localStorage).

## Controls

| Action | Key |
|---|---|
| Drive / walk | W A S D / arrow keys |
| Drift | Space |
| Nitro | Shift |
| Enter / exit car | F |
| Fire / interact | E |
| Outfit swap (at your car) | T |
| Garage | B |
| Radio on/off | R |

Touch buttons appear automatically on mobile screens.

## Tech

- [Three.js](https://threejs.org) (r128) via CDN for 3D rendering
- [PeerJS](https://peerjs.com) via CDN for multiplayer
- Vanilla JavaScript + WebAudio — everything else (city, textures, models) is generated procedurally in code at load time. There are **no external asset files**.

## Run it / deploy it

1. Take `index.html`.
2. Put it on any static host (Cloudflare Pages, Netlify, GitHub Pages, itch.io, your own server) — or just open it in a browser.
3. Done. (An internet connection is needed for the two CDN libraries and for multiplayer.)

An optional GitHub Actions workflow (`.github/workflows/build-android.yml`) wraps the game into an Android App Bundle for Google Play packaging.

## Customise it

Everything lives in the one file, in clearly commented sections:

- **Levels** — the `LEVELS` array: each level is `{ title, reward, setup(), getDesc(), isComplete() }`. Add, remove or re-balance missions in minutes.
- **Car prices & garage** — search for `personalCar` and the garage definitions.
- **City size / roads** — the world is built on a 50-unit grid; building, road and prop generation are in the world-building section.
- **Colours & branding** — the title, palette constants and HUD styles are plain CSS/JS values at the top of the file.
- **Ads (optional)** — a guarded CrazyGames SDK hook is included (safe no-op off-platform); a mid-game ad break fires on level transitions when the SDK is present.

## Notes

- All names, characters, vehicles and the city are original. No third-party game assets are used.
- Multiplayer uses PeerJS's public broker; for a commercial launch you can point PeerJS at your own PeerServer in one line.

## License

© KAUREX. All rights reserved. Supplied to buyers under the marketplace license of the store it was purchased from (single-project use unless stated otherwise).
