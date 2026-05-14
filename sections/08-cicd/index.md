---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

This section provides a conceptual description of the Continuous Integration and Continuous Delivery workflow adopted for the project.

The project uses GitHub as its main collaboration and automation platform. CI/CD is mainly exploited to automate quality checks, dependency management, release-related tasks, and the publication of the report website.

## What is automated?

The automation workflow covers the following activities:

- execution of automated tests;
- validation of the Python project after changes are pushed;
- dependency update management;
- release management through semantic versioning;
- deployment of the project report through GitHub Pages.

## Why?

CI/CD was introduced to make the development process more reliable and repeatable.

In particular, automation helps the team to:

- detect regressions early;
- ensure that new changes do not break existing features;
- keep dependencies under control;
- reduce manual work during release activities;
- make the report continuously available online.

This is especially useful in a collaborative project, where multiple developers work on different parts of the codebase.

## How?

The project relies on GitHub Actions to execute automated workflows when changes are pushed to the repository or when pull requests are created.

The test workflow installs the required Python dependencies and runs the project test suite. This ensures that the main components of the game, such as models, controllers, views, zombie logic, projectile behavior, and wave management, remain functional after each change.

Dependency management is supported by Renovate, configured through the `renovate.json` file. Renovate checks whether newer versions of the project dependencies are available and can propose updates automatically.

Release automation is supported by Semantic Release, configured through `release.config.js` and the Node.js configuration files. This allows the project to follow a structured versioning approach based on commit messages.

## GitHub Actions details

GitHub Actions is used as the automation engine of the project.

A typical CI execution includes the following steps:

1. checkout of the repository;
2. setup of the Python environment;
3. installation of project dependencies from `requirements.txt`;
4. installation of development dependencies from `requirements-dev.txt`, when needed;
5. execution of the automated test suite with `pytest`.

The report website is deployed through GitHub Pages. Every update pushed to the `main` branch of the report repository can be reflected in the online documentation site after GitHub Pages rebuilds the project.

## Secrets and environment variables

The game itself does not require runtime secrets or environment variables.

For CI/CD purposes, GitHub automatically provides the `GITHUB_TOKEN`, which can be used by GitHub Actions for repository-related operations.

If package publishing is enabled, additional secrets may be configured in the GitHub repository settings, for example a PyPI token used to publish releases. These secrets are stored securely in GitHub and are not committed to the repository.

## Summary

The CI/CD workflow supports the project by automating repetitive and error-prone tasks. It improves the reliability of the codebase, simplifies collaboration, and keeps the report continuously deployable through GitHub Pages.