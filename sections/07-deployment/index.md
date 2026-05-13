---
title: Deployment
has_children: false
nav_order: 8
---

# Deployment

This section describes the operations required to install and execute *Garden Invasion* on a user machine.

## User installation

The user must install Python in order to execute the application.

The recommended Python versions are:

- Python 3.12
- Python 3.13

The project has been tested and validated on both macOS and Windows environments.

### Required software

The following software is required:

- Python 3.12 or Python 3.13
- `pip`
- Git (optional, only required to clone the repository)

### Installation procedure

Clone the repository:

```bash
git clone https://github.com/unibo-dtm-se-2425-GardenInvasion/SoftwareArtifact.git
cd SoftwareArtifact
```

Create a virtual environment:

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

Install the required dependencies:

```bash
pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
```

If development and testing dependencies are required:

```bash
pip install -r requirements-dev.txt
```

Run the game with:

```bash
python -m GardenInvasion
```

### Configuration

No additional configuration files or environment variables are required.

All assets required by the game, including images and sounds, are already included in the repository under the `GardenInvasion/Assets` directory.

### Additional notes

During development, compatibility issues were encountered between `pygame==2.6.1` and Python 3.14 on macOS systems. For this reason, Python 3.12 or 3.13 is recommended.

In some macOS environments, SDL libraries may need to be installed manually:

```bash
brew install sdl2 sdl2_image sdl2_mixer sdl2_ttf pkg-config
```

## Server-side installation

No server-side installation is required.

*Garden Invasion* is a standalone desktop application and does not require:

- backend servers
- databases
- authentication services
- message brokers
- cloud infrastructure
- network communication

All game logic and resources are executed locally on the user machine.