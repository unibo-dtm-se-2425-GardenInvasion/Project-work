---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing approach

The project follows a **post-implementation testing** approach rather than strict Test-Driven Development. Tests were written in parallel with the implementation, covering all three layers of the MVC architecture: `Model`, `View`, and `Controller`. The testing framework used is Python's built-in **`unittest`**, invoked via:

```bash
python -m unittest discover -s test -t .
```

The CI workflow runs the full test suite in a matrix of **Python 3.12 and 3.13** across **Ubuntu, Windows, and macOS** on every push and pull request.

Since GardenInvasion relies on Pygame for rendering and audio, all tests that need a display or sound system set the SDL environment variables `SDL_VIDEODRIVER=dummy` and `SDL_AUDIODRIVER=dummy` to avoid requiring a real graphical session, which allows the suite to run correctly in headless CI environments.

## Testing (automated)

We have **~100 tests across 25 files**, all passing.

### Unit testing

Unit tests check **one class at a time**, in complete isolation. We tested all the core game entities: Player, Zombie, WallNut, Projectile, PowerUp, WaveManager, SettingsModel, SkinSelectionModel, and SoundManager.

What we covered:
- Player movement (F01), shoot cooldown (F02), and HP system regarding damage, destruction, and the constraint that life never goes below 0 (F05)
- Zombie types: RedZombie (1 HP, straight) and OrangeZombie (2 HP, zigzag), movement, damage, and screen bounds (F03, F04)
- WallNut HP and destruction (F06)
- WaveManager: correct zombie counts per wave, wave completion detection, and victory condition (F03, F13)
- PowerUp type and pickup (F07–F09)
- Settings and skin selection state (F10, F11)

To avoid loading real images, we replaced `pygame.image.load` with a dummy surface using `unittest.mock.patch` (a **stub**). Where a class needed a collaborator (e.g., `SettingsModel` passed to `Player`), we used `MagicMock` (a **mock**).

**Unit test success rate: 100%**

### Integration testing

Integration tests check **two or more components working together**. We tested Controller functions alongside real Model instances to confirm they interact correctly.

What we covered:
- Collision handlers: projectile→zombie, zombie→plant, zombie→wallnut focusing on correct damage, destruction signals, and no false positives (F04, F05, F06)
- Pause menu: keyboard and mouse navigation returning the correct outcome (`resume`, `menu`, `quit`) (F12)
- Volume controller: increases/decreases by 5, clamps at 0 and 100, changes propagate to the sound manager (F11)
- Plant movement and shooting (F01, F02), wallnut placement (F06), skin selection (F10), power-up collection (F07–F09)

We used `patch('pygame.sprite.spritecollide')` and `patch('pygame.sprite.groupcollide')` as **stubs** to control collision outcomes, and `MagicMock` as a **mock** to verify the right methods were called on the right objects.

**Integration test success rate: 100%**

### System testing

System tests check the **full rendering pipeline** by calling View functions with real Pygame surfaces. Since the game is graphical, full automation is limited, as a consequence these tests only focus on confirming the visual layer does not crash under any expected condition.

What we covered:
- `draw_game()` renders all sprites (player, projectiles, wallnuts, zombies) correctly, and handles empty or `None` groups without crashing (NF01, NF03)
- HUD heart display draws 0, 1, or 2 hearts correctly depending on life points (F05)
- All screens (menu, options, skin selection, victory) render without errors (F10–F14)
- All tests pass on Ubuntu, Windows, and macOS (NF04)

**System test success rate: 100%**

## Acceptance tests (manual)

The game's graphical interface cannot be fully tested automatically, so we verified the main gameplay scenarios by hand. 

| # | Scenario | Steps | Expected result | Result |
|---|---|---|---|---|
| AT-1 | Launch the game | Run `python -m GardenInvasion` | Main menu appears with New Game, Options, Quit |  Pass |
| AT-2 | Start a new game | Select "New Game" and press Enter | Game starts, player appears at the bottom, first wave spawns |  Pass |
| AT-3 | Player movement | Press ← and → during gameplay | Player moves left and right within screen bounds |  Pass |
| AT-4 | Player shooting | Press Space | A projectile fires from the player toward the zombies |  Pass |
| AT-5 | Zombie takes damage | Shoot a zombie | Zombie HP decreases; zombie disappears at 0 HP |  Pass |
| AT-6 | Player takes damage | Let a zombie reach the player | Player loses 1 life; HUD heart count decreases |  Pass |
| AT-7 | Place a wall-nut | Press the wall-nut key during gameplay | A WallNut appears in the available slot in front of the player |  Pass |
| AT-8 | Wall-nut absorbs damage | Let zombies attack a wall-nut | Wall-nut HP decreases; it disappears when destroyed |  Pass |
| AT-9 | Wave progression | Defeat all zombies in a wave | Next wave starts after a short delay |  Pass |
| AT-10 | Victory condition | Complete all 5 waves | Victory screen is displayed |  Pass |
| AT-11 | Game over | Let player HP reach 0 | Game over screen is displayed |  Pass |
| AT-12 | Pause menu | Press Escape during gameplay | Pause menu appears with Resume, Main Menu, Quit options |  Pass |
| AT-13 | Volume control | Go to Options → adjust volume slider | Music/SFX volume changes in real time |  Pass |
| AT-14 | Skin selection | Go to Options → select a different skin | New skin is applied to the player in the next session |  Pass |
| AT-15 | Power-up collection | Move the player over a spawned power-up | Power-up effect is applied (e.g., speed boost) |  Pass |

All 15 manual acceptance tests passed.