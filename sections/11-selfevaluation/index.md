---
title: Self-evaluation
has_children: false
nav_order: 12
---

# Self-evaluation

## Alessandro Filipelli

- **Role and contribution within the group**

  My role in the project was both conceptual and technical. I proposed the original idea of combining Space Invaders-style gameplay with a Plants vs. Zombies-inspired theme.

  From an implementation point of view, I mainly worked on the zombie and wave systems, including the zombie model, wave model, wave manager, the related controller logic, and the tests connected to these parts.

  I also implemented the two-life system for the plant and Wallnut during the work in progress phase, and added collision sound effects, such as the sounds connected to projectiles, zombies, and other collision events.

  In addition to the parts I directly developed, I contributed to the balancing and refinement of the game during manual testing. This included agreed changes to several gameplay parameters and components, such as Wallnut health values, controller behavior, difficulty values, and other elements that needed adjustment after trial runs. These changes were different from developing a feature from scratch, but they were important for making the final gameplay more balanced, challenging, and playable.

- **Strengths of the product and of my contribution**

  One strength of the product is its simplicity. The gameplay is straightforward and easy to understand, which fits the scope of the project and makes the game immediately playable.

  Another strength is the clear distinction between the different sections of the project, both in the gameplay structure and in the repository organization. I recognize that the clean organization of the repository was mainly my partner's contribution, but it still represents an important strength of the final product.

  Regarding my personal contribution, I think my biggest strength was idea generation. I contributed to shaping the initial concept and the gameplay ideas that were later translated into code and became part of the final game. My coding work was also an important part of my contribution, especially for the zombie and wave systems, but the strongest aspect of my role was developing and refining the ideas behind the gameplay.

- **Weaknesses and possible improvements**

  One weakness of the product is also connected to one of its strengths: its simplicity. For the context of an exam project, this simplicity is appropriate and consistent with the expected level of complexity. However, if the product is considered as a complete game, it would need to be much more structured and developed.

  At the moment, the game has only one level, the gameplay experience lasts only a few minutes, and replayability is limited because the wave pattern is fixed. A clear improvement would be to create multiple wave patterns and rotate them, so that each run feels less predictable and more varied.

  In a larger version of the project, the game could also include multiple levels connected by a simple narrative. This would make the experience feel more complete, allowing the player to progress through a small story or hero's journey. The visual side could also support this progression, with different backgrounds, enemy skins, shaders, and styles depending on the level or narrative phase.

  From a more technical gameplay perspective, future improvements could include new enemy types introduced as levels progress, power-ups, boss fights, status effects such as speed changes, buffs and debuffs, weapon customization, and a basic loadout system. These mechanics could start simple and gradually become more varied as the player advances through the game, increasing both depth and replayability.

## Filippo Malocco

- **Role and contribution within the group**

  My role in the group was primarily technical and organizational. I was responsible for setting up and maintaining the project infrastructure, including the repository structure, the CI/CD pipeline using GitHub Actions and semantic-release, the setup.py configuration for PyPI distribution, and the Renovate bot for automated dependency updates. 
  
  From an implementation perspective, I contributed to a large portion of the codebase across all three MVC layers. My most significant features include the menu and options system (main menu, options screen, volume control, skin selection), the game over and victory screens with fade-in animations, the heart display HUD, the zombie and projectile sprite rendering system, the power-up system (fire-rate boost and wallnut repair), and various collision system refinements such as removing the wallnut-projectile collision to allow plant projectiles to pass through freely. 
  
  I also wrote and maintained a substantial share of the test suite, including fixing timing issues in shooting cooldown tests and updating tests across multiple CI failures. 
  
  Throughout the project I was also responsible for code quality and cleanliness: I removed debug print statements, cleaned up comments, and resolved merge conflicts to keep the master branch stable and always releasable.

- **Strengths of the product and of my contribution**

  One strength of the product that I am particularly satisfied with is the overall polish of the user-facing screens. The menus, the game over and victory screens, and the HUD are consistent in style and respond correctly to both keyboard and mouse input, which gives the game a more complete feel despite its scope.
  
  Another strength is the engineering discipline of the project. The use of Conventional Commits, automated versioning via semantic-release, and a CI matrix with Python 3.12 and 3.13. This infrastructure made collaboration easier and ensured the product was always in a releasable state.
  
  Regarding my personal contribution, I believe my I think my overall understanding of the project: I was involved in every layer of the architecture (Model, View, Controller, tests, and CI) which gave me a complete picture of the system and allowed me to integrate components reliably.

- **Weaknesses and possible improvements**

  One weakness I recognize in my contribution is that, by being involved across so many areas, some individual features were implemented quickly without the depth they deserved. 
  
  The power-up system in particular is functional but minimal: there are only two power-up types, and the drop probability (currently 50%) was adjusted experimentally rather than through systematic playtesting. A more methodical approach to gameplay balancing would have produced a more refined experience.
  
  A technical weakness of the current product is the absence of persistent settings across sessions beyond volume and skin. Features such as a high score table or per-session statistics would add meaningful replayability and are straightforward to implement on top of the existing SettingsModel JSON persistence mechanism. 
