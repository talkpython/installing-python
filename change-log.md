# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased]

### Fixed
- **`python -V` now actually works after following the guide.** `uv python install 3.14` only creates a versioned `python3.14` executable, so the macOS and Linux verification steps told readers to run `python -V` and expect success when they'd get `command not found`. All three platforms now install with `--default`, which creates the `python` and `python3` executables the guide promises.
- Verification step is now consistent across Windows, macOS, and Linux (previously Windows used `uv run python -V` while macOS and Linux claimed bare `python -V` worked).
- Corrected sample command output, which showed a `Searching for Python 3.14` line that uv does not print and omitted the installed executable names.
- Updated Python version references from 3.14.2 to 3.14.6, and resolved the intro contradiction between "3.12+ is recommended" and installing 3.14.
- Rewrote the virtual environment explanation. It said "once activated, you can use `python` directly," which was only meaningful back when bare `python` didn't work at all. It now teaches what activation actually does: `python` switches from your global 3.14 to the project's interpreter, which may be a different version entirely.
- Refreshed the README, which still described the guide as a "complex decision tree" — the exact thing the 2025 rewrite eliminated. Also added Linux (the guide covers it), linked the changelog, and fixed punctuation.
- Fixed two silently-ignored keys in `.rumdl.toml`: `disabled-rules` → `disable` and `MD048.code-fence-style` → `MD048.style`. Because the disable list never loaded, the guide's intentional inline HTML was being flagged on every run.

### Added
- Note that `--default` emits an experimental warning, so readers don't think the install failed.
- Note that the patch version and install time in sample output will differ, so the page doesn't read as wrong the moment 3.14.7 ships.
- Warning against using `--default` when installing multiple Python versions, plus how to intentionally repoint `python` at a different version later.
- Explicit "close and reopen your terminal" reminder in each verification step.

## [2025.12.10] - python-2025-guide

### Changed
- **Completely modernized Python installation guide for 2025**
  - Replaced 10 different installation methods with unified uv approach
  - Simplified guide from 454 lines to ~256 lines
  - Updated target Python version from 3.12 to 3.14.2
  - Guide now works identically across Windows, macOS, and Linux
  
### Added
- Installation instructions using uv (one-command install per platform)
- Section on working with Python projects and virtual environments
- Section on managing multiple Python versions with uv
- "Why uv?" explanation section
- Link to Talk Python episode #476 about unified Python packaging with uv

### Removed
- Anaconda distribution installation instructions
- Chocolatey package manager for Windows
- Homebrew package manager for macOS
- Windows Store Python installation
- Official python.org installer instructions
- Building Python from source on Linux
- All pros/cons decision-making complexity
- Python 2.7 outdated version warnings (it's 2025!)

## Previous Versions

The guide existed prior to this changelog. This represents the first tracked release using the modernized uv-based approach.

