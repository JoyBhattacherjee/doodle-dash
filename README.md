# Doodle Dash

A hand-drawn endless runner built with React 18 and an HTML canvas game loop. Everything lives in a single `index.html`, so there is no build step.

## Play

Open `index.html` in a browser, or enable GitHub Pages (Settings → Pages → deploy from the `main` branch, root folder) and visit `https://joybhattacherjee.github.io/doodle-dash/`.

## Controls

| Action | Keyboard | Mouse |
| --- | --- | --- |
| Jump (hold for a higher hop) | Space, Up arrow or W | Click the game |
| Dash (short invincible burst) | Shift, D or Right arrow | Header button |
| Pause | P or Esc | Pause button |
| Mute | M | Sound button |
| Pick a character (menu) | 1, 2 or 3 | Click a card |

## On a phone

Turn the phone sideways and the game takes over the whole screen, like an app. Held upright, it asks you to rotate (or tap "Play in portrait anyway").

Two touch schemes, chosen on the menu and remembered:

- **Split tap**: tap the right half of the screen to jump (hold for a higher hop) and the left half to dash.
- **Tap + swipe**: tap anywhere to jump. Swipe right, or press the Dash button, to dash.

Small round buttons in the corner pause, mute and toggle fullscreen. Android phones get light vibration on stomps, power-ups and crashes.

### Install it as an app

The repo includes a web app manifest and a service worker, so the game can be installed and opens fullscreen in landscape, with no browser bars:

- **Android (Chrome):** menu → Install app (or Add to Home screen). The game locks to landscape.
- **iPhone (Safari):** Share → Add to Home Screen. iOS ignores orientation lock, so turn the phone sideways yourself.

After one online visit it also works offline.

## How it works

- Run forever across procedurally generated platforms. Speed and gap width grow over time.
- Dodge spikes, saws, bats and slugs, or stomp bats and slugs from above. Chained stomps score more.
- Pick one of three characters on the menu (Blobby, Whisk or Boxy). They look different but play the same.
- Collect coins and power-ups: Shield (absorbs one hit), Wings (double jump), Magnet (pulls in coins), Bolt (recharges dash).
- Your best score is saved in the browser with `localStorage`.

## Code layout

`index.html` has three parts:

1. **Engine** (between the `ENGINE START` and `ENGINE END` comments): a plain canvas game class with fixed-step physics, level generation, collisions and drawing.
2. **Sound and device helpers**: tiny WebAudio blips, vibration cues and fullscreen handling.
3. **React UI**: menus, HUD, keyboard, mouse and touch input, the character picker, and high score handling.

Other files: `manifest.webmanifest` and `icons/` (installable app), `sw.js` (offline cache).

React 18 is loaded from the cdnjs CDN.
