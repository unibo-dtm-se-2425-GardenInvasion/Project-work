---
title: Future work
has_children: false
nav_order: 13
---

# Known issues and future work

## What is missing

- **Replayability and content variety** -> The game currently has a single fixed wave pattern with five waves and no alternative level layouts or difficulty modes, so each run feels very similar once the player has learned the pattern.

- **Scoring and progression systems** -> There is no score, combo system, timer, or high-score table; each playthrough ends in a victory or game over screen without any persistent record of performance.

- **Richer enemy and power-up variety** -> The implementation focuses on a small set of zombie behaviours and two power-up effects (fire-rate boost and wallnut repair). More enemy archetypes, boss encounters, and additional power-ups (e.g., movement buffs, debuffs, or temporary shields) were discussed but not implemented.

- **In-game guidance and accessibility options** -> Controls are documented in the README but there is no in‑game tutorial, help screen, or accessibility features such as remappable controls, colour-blind-friendly palettes, or alternative UI scaling.

## What does not work as it should

- **Gameplay balancing of power-ups and difficulty** -> The probability of power-up drops and their impact on the game (e.g., fire-rate reduction and wallnut repair) were tuned empirically rather than based on systematic playtesting. The current 50% drop chance after a zombie is destroyed can make some runs noticeably easier than others and may not represent the intended balance described in the requirements.

- **Limited end-to-end test coverage of visual behaviour** -> The automated test suite is extensive and covers core model and controller logic, but many tests rely on mocks and dummy surfaces. This means some integration aspects of rendering and timing (for example, how sprite groups interact on screen) are only covered by manual acceptance tests rather than automated system tests.

## Potential future developments

- **Multiple levels, wave patterns, and difficulty modes** -> Introduce several level layouts and alternative wave sequences, rotating them randomly or based on difficulty selection to increase replayability and reduce predictability of enemy spawns.

- **Scoring, statistics, and progression** -> Add a scoring system (points per zombie type, bonuses for avoiding damage, streaks for consecutive hits), a high-score table stored using the existing JSON persistence approach, and basic per-session statistics such as enemies defeated and waves survived.

- **Expanded enemy and power-up design** -> Implement new enemy types (faster zombies, armoured zombies, ranged elites, mini-bosses, and bosses), as well as additional power-ups (temporary shields, movement speed modifiers, damage boosts, slow-motion effects). These could be introduced gradually across levels to create a sense of progression.

- **Improved UX and accessibility** -> Add an in‑game tutorial or help modal that summarises controls and mechanics, allow players to remap keys, and consider options such as larger fonts, higher-contrast UI themes, and optional screen shake toggles to accommodate different player preferences.

- **Stronger automated system tests** -> Complement the current unit and integration tests with a small set of automated system tests that drive Pygame via synthetic events, verifying that critical scenarios (e.g., wave transitions, game over and victory flows, pause menu) behave correctly in a more realistic environment.