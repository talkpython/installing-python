# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [Unreleased]

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

