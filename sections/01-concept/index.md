---
title: Concept
has_children: false
nav_order: 2
---

# Concept

## Type of Product

Garden Invasion is a **desktop application with a graphical user interface (GUI)**, built with Python and Pygame. It is a self-contained, single-player arcade game that runs locally on the user's machine. No browser, server, or internet connection is required.

## Use Case Collection

### Where are the users?
Users are casual gamers playing locally on their own PC or laptop. The game targets players who enjoy quick, reflex-based arcade sessions reminiscent of Space Invaders or Plants vs Zombies. Neither multiplayer nor online component exists.

### When and how frequently do they interact with the system?
Users interact with the game on demand, creating a single playthrough typically lasts a few minutes. There is no persistent progression that forces the user to return at scheduled times.

### How do they interact with the system? Which devices are they using?
Users interact via **keyboard** or **mouse** on a desktop or laptop computer:
- **Arrow Keys / WASD** — move the player plant left and right
- **Space / Enter** — confirm selections in menus
- **Mouse** — navigate the main menu (skin selection, options, volume)

The game targets any machine capable of running Python and PyGame, with no GPU or touchscreen requirements.

### Does the system need to store user data? Which data? Where?
The system stores a minimal amount of user preference data locally:
- **Selected skin** (Classic, Cactus, Carnivorous Plant)
- **Volume settings** (music and sound effects level)

This data is persisted on the local filesystem (e.g. a settings file) so that preferences are remembered between sessions. No personal data, account information, or gameplay statistics are collected or sent externally.

### Roles
There is only **one user role** in Garden Invasion:

| Role   | Description |
|--------|-------------|
| Player | 1. Launches the game, 2. customises their skin and audio settings, 3. plays the arcade game session. Has full control over all available interactions. |
