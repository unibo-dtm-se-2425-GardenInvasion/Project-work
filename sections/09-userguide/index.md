---
title: User guide
has_children: false
nav_order: 10
---

# User Guide

This section explains how to use *Garden Invasion* from the player perspective, assuming that the game has been correctly installed and configured.

## Starting the game

After installing the required dependencies, the game can be started from the root directory of the project with:

```bash
python -m GardenInvasion
```

When the application starts, the main menu is displayed.

---

## Main menu

The main menu contains two main options:

- **New Game**
- **Options**

The player can navigate through the menu using either the keyboard or the mouse.

### Keyboard controls

| Action | Keys |
|---|---|
| Move selection up | `W` or `↑` |
| Move selection down | `S` or `↓` |
| Confirm selection | `ENTER` or `SPACE` |

### Mouse controls

- Move the mouse over a menu item to highlight it.
- Left-click on a menu item to select it.

---

## Options menu

The options menu allows the player to customize the game experience.

The available options are:

- volume settings;
- skin personalization;
- contact section;
- return to the main menu.

### Volume settings

The volume menu allows the player to increase or decrease the game audio volume.

#### Controls

| Action | Keys |
|---|---|
| Decrease volume | `A` or `←` |
| Increase volume | `D` or `→` |
| Confirm and return | `ENTER` or `SPACE` |

Changes are saved automatically.

---

### Skin personalization

The skin personalization menu allows the player to select different visual appearances for the plant character.

Available skins include:

- Classic Plant
- Carnivorous Plant
- Cactus Plant

#### Controls

| Action | Keys |
|---|---|
| Previous skin | `A` or `←` |
| Next skin | `D` or `→` |
| Confirm skin | `ENTER` or `SPACE` |
| Return | `Back` button or mouse click |

The selected skin is saved and automatically loaded during gameplay.

---

### Contact section

The contact section allows the user to open their default email client in order to contact the development team.

---

## Gameplay

The objective of the game is to survive zombie attacks while protecting the player using wall-nuts and projectiles.

### Player movement

| Action | Keys |
|---|---|
| Move left | `A` or `←` |
| Move right | `D` or `→` |

The player can move horizontally across the screen.

---

### Shooting

The player shoots automatically based on an internal cooldown system.

Projectiles are generated periodically while the game is active.

---

### Wall-nut placement

Wall-nuts act as defensive barriers.

The player can place wall-nuts using the numeric keys:

| Wall-nut slot | Key |
|---|---|
| Slot 1 | `1` |
| Slot 2 | `2` |
| Slot 3 | `3` |
| Slot 4 | `4` |

Wall-nuts absorb enemy projectiles and can be destroyed after taking damage.

---

### Pause menu

Pressing `ESC` during gameplay opens the pause menu.

The pause menu contains three options:

- return to main menu;
- resume the game;
- quit the application.

#### Pause menu controls

| Action | Keys |
|---|---|
| Move selection | `A/D` or `←/→` |
| Confirm selection | `ENTER` or `SPACE` |
| Resume quickly | `ESC` |

---

## Exiting the game

The player can close the game by:

- pressing the window close button;
- selecting the quit option from the pause menu;
- confirming quit dialogs when requested.

---

## Notes

The game was designed to support both keyboard and mouse interaction throughout the entire user interface.

All settings, including selected skin and audio volume, are saved automatically between sessions.