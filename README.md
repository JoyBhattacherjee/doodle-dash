# Doodle Dash

A hand-drawn endless runner built with React 18 and an HTML canvas game loop. Everything lives in a single `index.html`, so there is no build step.

## Play

Open `index.html` in a browser, or enable GitHub Pages (Settings → Pages → deploy from the `main` branch, root folder) and visit `https://joybhattacherjee.github.io/doodle-dash/`.

## Controls

| Action | Keyboard | Touch |
| --- | --- | --- |
| Jump (hold for a higher hop) | Space, Up arrow or W | Tap the game |
| Dash (short invincible burst) | Shift, D or Right arrow | Dash button |
| Pause | P or Esc | Pause button |
| Mute | M | Sound button |

## How it works

- Run forever across procedurally generated platforms. Speed and gap width grow over time.
- Dodge spikes, saws, bats and slugs, or stomp bats and slugs from above. Chained stomps score more.
- Pick one of three characters on the menu (Blobby, Whisk or Boxy). They look different but play the same.
- Collect coins and power-ups: Shield (absorbs one hit), Wings (double jump), Magnet (pulls in coins), Bolt (recharges dash).
- Your best score is saved in the browser with `localStorage`.

## Code layout

`index.html` has three parts:

1. **Engine** (between the `ENGINE START` and `ENGINE END` comments): a plain canvas game class with fixed-step physics, level generation, collisions and drawing.
2. **Sound**: tiny WebAudio blips, started after the first tap or key press.
3. **React UI**: menus, HUD, keyboard and pointer input, and high score handling.

React 18 is loaded from the cdnjs CDN.
