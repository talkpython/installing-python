# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased]

### Added

- **Answer-first opening.** The guide now leads with the actual answer — install uv, then run `uv python install 3.14 --default` — before the welcome. Previously the first text was a greeting and the two commands didn't appear until a third of the way down, so anything quoting the top of the article (search snippets, AI assistants) found no answer to "how do I install Python."
- **Attribution and freshness line** under the title (last updated, Python version covered, author). Readers landing cold couldn't tell whether the guide was from 2019 or last week, which matters more here than on most pages because installing Python has changed so much.
- **Source link for the "10-100x faster than pip" claim**, pointing at Astral's published benchmarks. It was the most quotable number in the article and the only one with nothing behind it.
- **Alt text on the `python: command not found` screenshot.** It was the first element after the title and was announced as nothing at all to screen readers.

### Changed

- **Per-OS step headings are now self-contained.** `Step 1. Install uv` appeared three times identically, under Windows, macOS, and Linux, with different and mutually incompatible commands underneath. Anything that reads the article by section — including AI assistants — had three identically-labeled sections to choose from, and could hand a Windows reader the `curl` command. Each heading now names its OS (`Step 1. Install uv on Windows`), and the OS `##` headings match how people actually search ("How to Install Python on Windows"). The hand-rolled `#windows` / `#macos` / `#linux` jump-link anchors are unaffected.

## [2026.07.16] - python-default-flag

### Fixed

- **`python -V` now actually works after following the guide.** `uv python install 3.14` only creates a versioned `python3.14` executable, so the macOS and Linux verification steps told readers to run `python -V` and expect success when they'd get `command not found`. All three platforms now install with `--default`, which creates the `python` and `python3` executables the guide promises.
- Verification step is now consistent across Windows, macOS, and Linux (previously Windows used `uv run python -V` while macOS and Linux claimed bare `python -V` worked).
- Corrected sample command output, which showed a `Searching for Python 3.14` line that uv does not print and omitted the installed executable names.
- Updated Python version references from 3.14.2 to 3.14.6, and resolved the intro contradiction between "3.12+ is recommended" and installing 3.14.
- Rewrote the virtual environment explanation. It said "once activated, you can use `python` directly," which was only meaningful back when bare `python` didn't work at all. It now teaches what activation actually does: `python` switches from your global 3.14 to the project's interpreter, which may be a different version entirely.
- Refreshed the README, which still described the guide as a "complex decision tree". That's the exact thing the 2025 rewrite eliminated. Also added Linux (the guide covers it), linked the changelog, and fixed punctuation.
- Fixed two silently-ignored keys in `.rumdl.toml`: `disabled-rules` → `disable` and `MD048.code-fence-style` → `MD048.style`. Because the disable list never loaded, the guide's intentional inline HTML was being flagged on every run.
- Stopped `rumdl fmt` from rewriting the repo link to display `https://GitHub.com/...`. MD044's proper-name rule was capitalizing the URL in the link text on every run. The link text is now descriptive rather than a raw URL.

### Added

- Note that `--default` emits an experimental warning, so readers don't think the install failed.
- Note that the patch version and install time in sample output will differ, so the page doesn't read as wrong the moment 3.14.7 ships.
- Warning against using `--default` when installing multiple Python versions, plus how to intentionally repoint `python` at a different version later.
- `PATH` troubleshooting fallback in each verification step, phrased per platform, for anyone whose terminal hasn't picked up the new executables.

### Changed

- Prose pass over the guide and README: replaced em dashes with plain hyphens or shorter sentences, tightened the `--default` explanation, and corrected the "two steps" promise that was followed by three.
- Applied `rumdl fmt` for consistent list markers, horizontal rules, and blank lines.

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
