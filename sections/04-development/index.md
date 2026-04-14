---
title: Development
has_children: false
nav_order: 5
---

# Development

## DVCS

The project uses **Git** as the distributed version control system, hosted on **GitHub** under the [unibo-dtm-se-2425-GardenInvasion](https://github.com/unibo-dtm-se-2425-GardenInvasion) organization.

### Branch conventions

The repository maintains two long-lived branches:
- **`master`**: the stable, production-ready branch. Releases are triggered automatically from this branch.
- **`main`**: used as an alternative integration branch.

### Commit message conventions

The project adopts the **Conventional Commits** specification, enforced through the `semantic-release-preconfigured-conventional-commits` package. Commit messages follow this format:

<type>(<scope>): <short description>

Common types include:
- `feat`: a new feature (triggers a minor release)
- `fix`: a bug fix (triggers a patch release)
- `chore`: maintenance tasks
- `docs`: documentation changes
- `test`: adding or fixing tests
- `ci`: changes to CI/CD configuration
- `BREAKING CHANGE`: breaking API changes (triggers a major release)

## Implementation details

### Network protocols

GardenInvasion is a **single-player local desktop game**. No network communication is required at runtime, meaning that there is no client-server architecture, no multiplayer, and no remote data exchange. Therefore, no network protocol is used or needed.

### In-transit data representation

Since there is no network communication, no in-transit serialization format (JSON, XML, Protocol Buffers, etc.) is required. Game assets (images, sounds) are loaded directly from the local filesystem using Pygame's built-in asset loading APIs.

### Database

The game does not use a database. All game state is held in memory during runtime.

### Authentication

No authentication mechanism is required.

### Authorization

No authorization mechanism is required. There are no roles or permissions.

## Technological details

### Programming language and framework

- **Python 3.12 / 3.13**: the primary programming language, chosen for its simplicity, readability, and the maturity of the Pygame ecosystem for 2D game development. The minimum supported version is defined in `.python-version`.
- **Pygame 2.6.1**: the core game development library, responsible for rendering graphics, handling keyboard/mouse input, playing audio, and managing the game loop.

The architecture follows the **MVC (Model-View-Controller)** pattern, reflected in the `GardenInvasion/Model/`, `GardenInvasion/View/`, and `GardenInvasion/Controller/` package structure, with a `GardenInvasion/Utilities/` package for shared helpers and `GardenInvasion/Assets/` for game resources.

### Libraries and dependencies

| Library | Version | Purpose |
|---|---|---|
| `pygame` | 2.6.1 | Game rendering, input, audio, and loop management |
| `setuptools` | ≥80.9.0 | Python package building and distribution |
| `pytest` | ≥8.3.4 | Unit and integration testing (dev only) |
| `build` | ≥1.0.0 | PEP 517 package building (dev only) |
| `twine` | ≥4.0.0 | Publishing releases to PyPI (dev only) |

### External tools and services

- **GitHub Actions**: CI/CD pipeline defined in `.github/workflows/check.yml` and `deploy.yml`. On every push, tests run in a matrix across Ubuntu, Windows, and macOS with Python 3.12 and 3.13.
- **semantic-release**: automated versioning and changelog generation based on Conventional Commits, configured in `release.config.js`. Releases are published to **PyPI** automatically on merges to `master`.
- **Renovate**: automated dependency update bot configured via `renovate.json`, which opens pull requests to keep dependencies up to date.
- **PyPI**: the package is distributed publicly on the Python Package Index under the name `unibo-dtm-se-2425-GardenInvasion`.