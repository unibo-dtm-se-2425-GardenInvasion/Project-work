---
title: Developer Guide
has_children: false
nav_order: 11
---

# Developer Guide

This section explains how a new contributor can join the development process of *Garden Invasion* and start contributing to the project.

## Project organization

The project is organized as a standard Python package.

The repository is divided into multiple components:

- `Controller/`
- `Model/`
- `View/`
- `Utilities/`
- `Assets/`
- `test/`

The architecture follows a simplified MVC-inspired organization:

- **Models** manage game logic and data;
- **Views** handle rendering and user interface;
- **Controllers** manage interactions between models and views.

The `Assets` directory contains all game resources such as images and sounds.

---

## Repository access and collaboration

The project is hosted on GitHub.

Main repositories:

- Software artifact repository;
- Project report repository.

Contributors can collaborate through:

- feature branches;
- pull requests;
- issue tracking;
- code reviews.

Issues and bugs can be reported through the GitHub Issues section of the repository.

---

## Development environment setup

### Required software

The following software is required for development:

- Python 3.12 or Python 3.13
- `pip`
- Git

Optional but recommended:

- Visual Studio Code
- PyCharm

---

### Clone the repository

```bash
git clone https://github.com/unibo-dtm-se-2425-GardenInvasion/SoftwareArtifact.git
cd SoftwareArtifact
```

---

### Create a virtual environment

```bash
python3.12 -m venv venv
```

Activate the virtual environment.

On macOS/Linux:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

---

### Install dependencies

Install runtime dependencies:

```bash
pip install -r requirements.txt
```

Install development dependencies:

```bash
pip install -r requirements-dev.txt
```

---

## Running the project

The game can be executed with:

```bash
python -m GardenInvasion
```

---

## Running the test suite

The project includes automated tests for models, controllers, views, and gameplay components.

Tests can be executed with:

```bash
pytest
```

Specific test files can also be executed individually:

```bash
pytest test/test_wave_model.py
```

---

## Coding conventions

The team follows a set of internal conventions in order to keep the codebase readable and maintainable.

### Naming conventions

- classes use `PascalCase`;
- methods and variables use `snake_case`;
- constants use `UPPER_CASE`.

Examples:

```python
class WallNutManager:
    pass

player_position = (100, 200)

SCREEN_WIDTH = 600
```

---

### File organization

The project separates logic according to responsibility:

| Directory | Responsibility |
|---|---|
| `Model` | game logic and entities |
| `View` | rendering and UI |
| `Controller` | input handling and orchestration |
| `Utilities` | shared constants and helpers |
| `Assets` | images and sounds |
| `test` | automated tests |

---

### Code style

The project generally follows Python best practices and a PEP8-inspired coding style.

Important practices include:

- meaningful variable names;
- modular functions;
- separation of concerns;
- inline comments for non-trivial logic.

---

## Development workflow

### Creating a feature branch

New features should be developed in dedicated branches.

Example:

```bash
git checkout -b feature/new-zombie-behavior
```

---

### Commit conventions

Contributors are encouraged to write clear and concise commit messages.

Examples:

```bash
git commit -m "Add zombie projectile collisions"
git commit -m "Fix pause menu navigation"
```

---

### Pull requests

Completed features should be submitted through pull requests.

Pull requests should:

- clearly describe the implemented feature;
- explain important design decisions;
- pass automated tests before merging.

---

## CI/CD workflow

The project uses GitHub Actions for Continuous Integration and Continuous Delivery.

Automation includes:

- execution of automated tests;
- dependency validation;
- release support;
- deployment of the report website through GitHub Pages.

The CI/CD workflow helps maintain code quality and reduce integration problems between contributors.

---

## Development tools

### Visual Studio Code

The project can be developed using Visual Studio Code with the following recommended extensions:

- Python extension;
- Pylance;
- GitHub Pull Requests;
- Markdown Preview.

---

### Command-line usage

Most development operations are executed through the terminal, including:

- virtual environment management;
- dependency installation;
- running tests;
- Git operations.

---

## Notes for contributors

Before submitting new code, contributors should:

- run the complete test suite;
- verify that the game launches correctly;
- ensure that no unnecessary files are committed;
- keep assets organized inside the `Assets` directory.

The project was designed to remain modular and easily extensible for future gameplay features.