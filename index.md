---
title: Home
layout: home
has_children: false
nav_order: 1
---

# Project title

### Authors

- [Alessandro Filipelli](mailto:alessandro.filipelli@studio.unibo.it)
- [Filippo Malocco](mailto:filippo.malocco@studio.unibo.it)

## Abstract

Garden Invasion is a software engineering project that fuses the arcade immediacy of Space Invaders with the “plants vs zombies” theme into a single action-focused experience.
​
Instead of placing static defenses on a grid (classic tower defense), the player directly controls one plant that moves left/right along the bottom of the screen, turning defense into a reflex-based shooter.
​
The gameplay is built around three pillars: shooting, evasion, and wave management, with enemy waves increasing in difficulty over time.
​
Key gameplay elements include:
- ​Player customization via skin selection (Classic, Cactus, Carnivorous Plant) and simple controls (Arrow Keys/WASD movement, automatic fire, Space/Enter for interactions).
​- A wave system that spawns zombies using timer-based logic, creating escalating pressure similar to classic arcade pacing.
​- A defensive “powerup” concept through Wallnuts: they have health, absorb projectile damage for the player, and can be rapidly destroyed if zombies reach and “eat” them.

Technically, the project is implemented in Python using Pygame and follows a Model–View–Controller (MVC) structure to keep logic, rendering, and input handling separated.
​
It relies on Pygame’s sprite system (pygame.sprite.Sprite and pygame.sprite.Group) for efficient entity management, plus rectangular collision checks (pygame Rect.colliderect) to handle hits between projectiles, zombies, and defenses.

## Disclaimer

During the preparation of this work, the authors used Claude Sonnet and Gemini to assist with debugging CI/CD errors, resolving Pygame audio initialization issues, refactoring code to adhere to the MVC pattern and configuring and personalizing test cases to ensure comprehensive code coverage.

All outputs produced by these tools were then personally reviewed, analyzed row by row, and carefully adapted to the specific needs and constraints of this project.

The authors take full responsibility for the content of the final report/artifact.

