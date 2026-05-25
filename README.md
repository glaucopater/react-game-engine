# React Shooter Game Engine

[![Netlify Status](https://api.netlify.com/api/v1/badges/43279ffe-701c-4a87-82ec-d1c860db5ccd/deploy-status)](https://app.netlify.com/sites/vitets-react-game/deploys)

Top-down grid shooter built with React and TypeScript.

**Live demo:** https://vitets-react-game.netlify.app

![Demo](/public/demo.png)

## Features

- **Main menu** with local high-score table (3-letter name, score, level, date)
- **4 levels** with unique backgrounds (`terrain1` → `terrain3`, then `space1`)
- **20 kills per level** to advance; difficulty scales each level
- **Random walls** that block movement and line-of-sight
- **Smooth enemy movement** with wall sliding
- **Power-ups**
  - Ammo
  - Random food energy pickups
  - Special weapons: Pierce Rifle, Shotgun, Ricochet Rifle
  - Power-ups despawn after 7 seconds if not collected (fade-out effect)
- **Bombs** spawn on the map; shoot them to trigger an explosion and temporary fire zone
- **Pause / game over / level complete** modals with return to main menu

## Controls

| Action | Input |
|--------|--------|
| Move | Arrow keys, WASD, or on-screen buttons |
| Shoot | Click in the game area |
| Pause | Spacebar or Pause button |

## Getting started

Requirements: Node.js 22+ and Yarn 4.

```bash
yarn install
yarn dev
```

Other scripts:

```bash
yarn build      # production build
yarn preview    # preview production build
yarn typecheck  # TypeScript check
yarn test       # run tests (Vitest)
yarn lint       # ESLint
```

## Gameplay

1. Start from the **main menu** and try to set a high score.
2. Eliminate **20 enemies** to complete the current level.
3. Collect **ammo** and **food** to restore bullets and health.
4. Pick up **special weapons** for limited powerful shots.
5. Shoot **bombs** to clear enemies with fire bursts.
6. Beat all **4 levels** to win. On game over or victory, qualify for the high-score board if your total score is high enough.

## Tech stack

- React 19 + TypeScript
- Vite 8
- Vitest + React Testing Library + happy-dom
- LocalStorage for high scores

## Project structure

```
src/
  components/   # UI and game entities (Area, Player, Enemy, Bomb, etc.)
  hooks/        # Game logic (enemies, power-ups, bombs, game state)
  helpers/      # Shared utilities (collision, spawning, aiming)
  constants/    # Game balance and assets
  features/     # Feature flags
```

## Configuration

Optional environment variables (see `.env.sample`):

```env
VITE_ALLOW_ENEMIES="true"
VITE_ALLOW_POWERUPS="true"
VITE_ALLOW_PLAYER_IMMORTAL="false"
```

Feature flags are currently defined in `src/features/index.ts`.

## Credits

Sound effects from [Pixabay](https://pixabay.com/sound-effects/):

- [floraphonic](https://pixabay.com/users/floraphonic-38928062/) — power-up sparkle
- Pixabay — reload, shotgun, damage sounds

Terrain and space background images are included in `src/assets/images/`.
