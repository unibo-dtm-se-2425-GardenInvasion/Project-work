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

`unittest` was chosen because it is part of the Python standard library, without the need for extra dependency, and it provides rich assertion methods along with `unittest.mock` for isolating components. The CI workflow runs the full test suite in a matrix of **Python 3.12 and 3.13** across **Ubuntu, Windows, and macOS** on every push and pull request.

Since GardenInvasion relies on Pygame for rendering and audio, all tests that need a display or sound system set the SDL environment variables `SDL_VIDEODRIVER=dummy` and `SDL_AUDIODRIVER=dummy` to avoid requiring a real graphical session, which allows the suite to run correctly in headless CI environments.

## Testing (automated)

> General recommendation: when discussing the tests below, please track to which requirement each test is related to.

### Unit testing

- Describe the unit tests you developed, and their rationale
- Report success rate and test coverage here

### Integration testing

- Describe couples of components that you tested together, and the corresponding test rationale/plan

- Report success rate and test coverage here

- If you used [test doubles](https://en.wikipedia.org/wiki/Test_double), describe her which type of double you used, and why

### System testing

- Describe the tests that you developed to automatically test the system as a whole
    + and the corresponding test rationale/plan
    + better would be to have system tests that match the acceptance criteria of the requirements

- Report success rate and test coverage here

- If you adopted containers (e.g. Docker compose) for testing, describe how you used them here
    + e.g. to run the system in a clean environment, or to run the tests in a clean environment

## Acceptance tests (manual)

- If you did any manual testing, describe it here
- Report the test rationale/plan so that another person can repeat the tests
    + better would be for acceptance tests to match the acceptance criteria of the requirements
- Report success rate here

