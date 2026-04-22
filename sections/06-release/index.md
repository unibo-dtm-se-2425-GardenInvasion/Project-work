---
title: Release
has_children: false
nav_order: 7
---

# Release

The project produces **one artefact**: a Python package named `unibo-dtm-se-2425-GardenInvasion`, built from the source code using `python -m build`. It is released onto **PyPI**. 

## How releases work

Releases are **fully automatic**. Every time a commit is pushed to the `master` branch and all CI tests pass, the deploy workflow runs `semantic-release`. 

No manual steps are needed to publish a release. The only configuration required is setting two GitHub repository secrets: `PYPI_USERNAME` and `PYPI_PASSWORD`.

## Choice of the license

The project is released under the **Apache 2.0 License**. This was chosen because it is a permissive open-source license that allows anyone to use, modify, and distribute the software freely, while still protecting contributors from patent claims. Both the code and the distributed artefact use the same license.

## Choice of the versioning schema

The project uses **Semantic Versioning**: `MAJOR.MINOR.PATCH`.

- **PATCH** (e.g. `1.0.0` → `1.0.1`): a bug fix commit (`fix:`)
- **MINOR** (e.g. `1.0.1` → `1.1.0`): a new feature commit (`feat:`)
- **MAJOR** (e.g. `1.9.0` → `2.0.0`): a breaking change (commit contains `BREAKING CHANGE`)

Semantic Versioning was chosen because it communicates intent clearly, allowinf the users to immediately tell from the version number whether an update is safe to apply or introduces new behaviour.

Version numbers are determined **automatically** by `semantic-release` based on Conventional Commits. The current latest version is **1.9.0**. Key milestones include:

| Version | Date | What changed |
|---|---|---|
| 1.0.0 | 2025-12-30 | Initial release: core game, audio, skin system, CI setup |
| 1.1.0 | 2026-01-15 | 2-life-point system for plant and wallnuts |
| 1.2.0 | 2026-01-16 | Plant projectile vs zombie collision |
| 1.3.0 | 2026-01-17 | Zombie projectile vs plant collision |
| 1.4.0 | 2026-01-18 | Game over screen with fade-in animation |
| 1.5.0 | 2026-02-05 | Sprite rendering for zombies and projectiles |
| 1.7.0 | 2026-02-14 | Heart display HUD |
| 1.8.0 | 2026-02-15 | Victory screen with fade-in animation and sound |
| 1.9.0 | 2026-02-22 | Power-up system (fire rate boost + wallnut repair) |