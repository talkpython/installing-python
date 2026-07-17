# How to Install Python 3.14 with uv

<img src="https://training.talkpython.fm/static/img/cms/python-not-found.webp" alt="A terminal window showing a 'python: command not found' error — the problem this guide solves" style="border-radius: 10px; display: block;" class="img img-responsive" />

**Last updated:** July 16, 2026 · **Covers:** Python 3.14 · **By:** [Michael Kennedy](https://talkpython.fm/), host of the [Talk Python To Me](https://talkpython.fm/) podcast

tl;dr; **To install Python 3.14 on Windows, macOS, or Linux, you run two commands:** first install [uv](https://docs.astral.sh/uv/), then run `uv python install 3.14 --default`. That's the whole process - no installer wizard, no decision tree, no editing your `PATH`, and the same two steps on every operating system. Copy-paste instructions for each platform are below.
<hr>

Welcome, soon-to-be Python user! Python is one of the easiest programming languages to learn and grow with. But there can be a bump right at the beginning: **making sure you have Python installed** with a sufficiently new version (3.14 is the current release, and it's what we'll install below).

The good news is that these days, installing Python is incredibly simple thanks to **[uv](https://docs.astral.sh/uv/)**, a blazing-fast Python package and project manager that also handles Python installation. With uv, you get **one tool** that works the same way on Windows, macOS, and Linux. [Hear all about it](https://talkpython.fm/episodes/show/476/unified-python-packaging-with-uv) on Talk Python.

## The Modern Approach: Install uv, Then Python

The process is just two commands:

1. **Install uv** (one command)
2. **Install Python with uv** (one command)

That's it! Jump to your operating system to get started:

- [**Windows**](#windows)
- [**macOS**](#macos)
- [**Linux**](#linux)<a id="windows" style="margin-bottom: 10px; display: inline-block;"></a>

<hr>

## How to Install Python on Windows

### Step 1. Install uv on Windows

Open [**PowerShell**](https://learn.microsoft.com/en-us/powershell/scripting/windows-powershell/starting-windows-powershell) or [**Windows Terminal**](https://apps.microsoft.com/detail/9n0dx20hk701) and run:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

After installation completes, **close and reopen your terminal** for the changes to take effect.

### Step 2. Install Python on Windows

Now install Python 3.14 with a single command:

```powershell
uv python install 3.14 --default
```

The `--default` flag gives you a plain `python` command rather than only `python3.14`, so this becomes the Python you get from now on.

You'll see output like:

```text
Installed Python 3.14.6 in 2.1s
 + cpython-3.14.6-windows-x86_64-none (python, python3, python3.14)
```

Your exact patch version and install time will differ. Python ships regular patch releases, so 3.14.7 or later is just as good. uv also prints a `warning:` noting that `--default` is experimental. That's expected, and nothing is wrong. The flag works; it just isn't finalized yet.

### Step 3. Verify Python Works on Windows

```powershell
python -V
```

You should see:

```text
Python 3.14.6
```

If PowerShell says `python` isn't recognized, close and reopen your terminal so it picks up the updated `PATH`, then try again.

**You're all set!** 🎉<a id="macos" style="margin-bottom: 10px; display: inline-block;"></a>
<hr>

## How to Install Python on macOS

### Step 1. Install uv on macOS

Open the [**Terminal**](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac) and run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

After installation completes, **close and reopen your terminal** for the changes to take effect.

### Step 2. Install Python on macOS

Now install Python 3.14 with a single command:

```bash
uv python install 3.14 --default
```

The `--default` flag gives you a plain `python` command rather than only `python3.14`, so this becomes the Python you get from now on.

You'll see output like:

```text
Installed Python 3.14.6 in 1.9s
 + cpython-3.14.6-macos-aarch64-none (python, python3, python3.14)
```

Your exact patch version and install time will differ. Python ships regular patch releases, so 3.14.7 or later is just as good. uv also prints a `warning:` noting that `--default` is experimental. That's expected, and nothing is wrong. The flag works; it just isn't finalized yet.

### Step 3. Verify Python Works on macOS

```bash
python -V
```

You should see:

```text
Python 3.14.6
```

If you get a `command not found` error, close and reopen your terminal so it picks up the updated `PATH`, then try again.

**You're all set!** 🎉<a id="linux" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## How to Install Python on Linux

### Step 1. Install uv on Linux

Open a [**terminal**](https://ubuntu.com/tutorials/command-line-for-beginners) and run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

After installation completes, **close and reopen your terminal** (or run `source ~/.bashrc` or `source ~/.zshrc`) for the changes to take effect.

### Step 2. Install Python on Linux

Now install Python 3.14 with a single command:

```bash
uv python install 3.14 --default
```

The `--default` flag gives you a plain `python` command rather than only `python3.14`, so this becomes the Python you get from now on.

You'll see output like:

```text
Installed Python 3.14.6 in 1.5s
 + cpython-3.14.6-linux-x86_64-gnu (python, python3, python3.14)
```

Your exact patch version and install time will differ. Python ships regular patch releases, so 3.14.7 or later is just as good. uv also prints a `warning:` noting that `--default` is experimental. That's expected, and nothing is wrong. The flag works; it just isn't finalized yet.

### Step 3. Verify Python Works on Linux

```bash
python -V
```

You should see:

```text
Python 3.14.6
```

If you get a `command not found` error, close and reopen your terminal (or run `source ~/.bashrc` or `source ~/.zshrc`) so it picks up the updated `PATH`, then try again.

**You're all set!** 🎉
_________________________

## Working with Python Projects

Once you have uv installed, you'll typically work within **virtual environments** for your projects. uv makes this simple:

### Creating a Virtual Environment

Navigate to your project folder and run:

```bash
uv venv --python 3.14
```

This creates a `.venv` folder in your project. If Python 3.14 isn't already installed, **uv will automatically download and install it for you**. On a fast connection, this can take as little as 2-3 seconds.

### Activating the Virtual Environment

**Windows (PowerShell):**

```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
source .venv/bin/activate
```

Activating doesn't just make `python` available - it changes which interpreter `python` points to. Instead of the global 3.14 you installed earlier, you get this project's own Python, which can be an entirely different version:

```bash
python -V
```

In a project created with `uv venv --python 3.12`, that reports:

```text
Python 3.12.13
```

When you're finished working on the project, run `deactivate` and `python` goes back to your global 3.14.

### Installing Packages

With uv, installing packages is lightning fast:

```bash
uv pip install requests
```

Or add dependencies to a project:

```bash
uv add requests
```
_________________________

## Managing Multiple Python Versions

Need multiple Python versions? uv handles that too:

```bash
uv python install 3.12 3.13 3.14
```

Note there's no `--default` here. Only one version at a time can own the plain `python` command, so leave `--default` off when installing extra versions. Otherwise you'll quietly repoint `python` at whichever version you installed last. Each version is always reachable by its full name (`python3.12`, `python3.13`) regardless.

List installed versions, including any that came with your system:

```bash
uv python list
```

Create a virtual environment with a specific version:

```bash
uv venv --python 3.12
```

Want to move `python` to a different version later? Re-run the install with `--default`:

```bash
uv python install 3.13 --default
```
_________________________

## Why uv?

**[uv](https://docs.astral.sh/uv/)** is developed by [Astral](https://astral.sh/), the creators of [Ruff](https://docs.astral.sh/ruff/) (the popular Python linter). It's designed to be:

- ⚡️ **Blazing fast** - 10-100x faster than pip ([see Astral's benchmarks](https://github.com/astral-sh/uv/blob/main/BENCHMARKS.md))
- 🐍 **Python version manager** - installs and manages Python itself
- 📦 **Package manager** - replaces pip, pip-tools, and virtualenv
- 🔒 **Lockfile support** - reproducible environments
- 🖥️ **Cross-platform** - works identically on Windows, macOS, and Linux

One tool. No complexity. Just Python.
_________________________

## Corrections and Improvements

If you find a problem or have a suggestion to make this page better, please open an issue on GitHub. Note that this is not intended for tech support but rather for genuine, broadly applicable improvements to the instructions:

[**https://github.com/talkpython/installing-python**](https://github.com/talkpython/installing-python)

<style>
hr {	margin-top: 0px;	}
.landing-cms ul,.landing-cms ol {	margin-bottom:.5em;	}
</style>