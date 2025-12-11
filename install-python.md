# Installing Python 3

<img src="https://training.talkpython.fm/static/img/cms/nopy-final.jpg" style="border-radius: 10px; display: block;" class="img img-responsive" />

Welcome soon-to-be Python user! Python is one of the easiest programming languages to learn and grow with. But there can be a bump right at the beginning: **making sure you have Python installed** with a sufficiently new version (3.12+ is recommended these days).

Good news! In 2025, installing Python has become incredibly simple thanks to **[uv](https://docs.astral.sh/uv/)** -- a blazing-fast Python package and project manager that also handles Python installation. With uv, you get **one tool** that works the same way on Windows, macOS, and Linux. [Hear all about it](https://talkpython.fm/episodes/show/476/unified-python-packaging-with-uv) on Talk Python.

## The Modern Approach: Install uv, Then Python

The process is just two steps:

1. **Install uv** (one command)
2. **Install Python with uv** (one command)

That's it! Jump to your operating system to get started:

* [**Windows**](#windows)
* [**macOS**](#macos)
* [**Linux**](#linux)

<a id="windows" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## Windows

### Step 1. Install uv

Open [**PowerShell**](https://learn.microsoft.com/en-us/powershell/scripting/windows-powershell/starting-windows-powershell) or [**Windows Terminal**](https://apps.microsoft.com/detail/9n0dx20hk701) and run:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

After installation completes, **close and reopen your terminal** for the changes to take effect.

### Step 2. Install Python

Now install Python 3.14 with a single command:

```powershell
uv python install 3.14
```

You'll see output like:

```
Searching for Python 3.14
Installed Python 3.14.2 in 2.34s
 + cpython-3.14.2-windows-x86_64-none
```

### Step 3. Verify It Works

```powershell
uv run python -V
```

You should see:

```
Python 3.14.2
```

**You're all set!** 🎉

<a id="macos" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## macOS

### Step 1. Install uv

Open the [**Terminal**](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac) and run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

After installation completes, **close and reopen your terminal** for the changes to take effect.

### Step 2. Install Python

Now install Python 3.14 with a single command:

```bash
uv python install 3.14
```

You'll see output like:

```
Searching for Python 3.14
Installed Python 3.14.2 in 1.89s
 + cpython-3.14.2-macos-aarch64-none
```

### Step 3. Verify It Works

```bash
python -V

# or

uv run python -V
```

You should see:

```
Python 3.14.2
```

**You're all set!** 🎉

<a id="linux" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## Linux

### Step 1. Install uv

Open a [**terminal**](https://ubuntu.com/tutorials/command-line-for-beginners) and run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

After installation completes, **close and reopen your terminal** (or run `source ~/.bashrc` or `source ~/.zshrc`) for the changes to take effect.

### Step 2. Install Python

Now install Python 3.14 with a single command:

```bash
uv python install 3.14
```

You'll see output like:

```
Searching for Python 3.14
Installed Python 3.14.2 in 1.52s
 + cpython-3.14.2-linux-x86_64-gnu
```

### Step 3. Verify It Works

```bash
python -V

# or 

uv run python -V
```

You should see:

```
Python 3.14.2
```

**You're all set!** 🎉

_________________________

## Working with Python Projects

Once you have uv installed, you'll typically work within **virtual environments** for your projects. uv makes this simple:

### Creating a Virtual Environment

Navigate to your project folder and run:

```bash
uv venv --python 3.14
```

This creates a `.venv` folder in your project. If Python 3.14 isn't already installed, **uv will automatically download and install it for you**.

### Activating the Virtual Environment

**Windows (PowerShell):**
```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux:**
```bash
source .venv/bin/activate
```

Once activated, you can use `python` directly:

```bash
python -V
```

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

List installed versions:

```bash
uv python list
```

Create a virtual environment with a specific version:

```bash
uv venv --python 3.12
```

_________________________

## Why uv?

**[uv](https://docs.astral.sh/uv/)** is developed by [Astral](https://astral.sh/), the creators of [Ruff](https://docs.astral.sh/ruff/) (the popular Python linter). It's designed to be:

- ⚡️ **Blazing fast** -- 10-100x faster than pip
- 🐍 **Python version manager** -- installs and manages Python itself
- 📦 **Package manager** -- replaces pip, pip-tools, and virtualenv
- 🔒 **Lockfile support** -- reproducible environments
- 🖥️ **Cross-platform** -- works identically on Windows, macOS, and Linux

One tool. No complexity. Just Python.

-------------------------------

## Corrections and Improvements

If you find a problem or have a suggestion to make this page better, please visit the GitHub repository here. Note that this is not intended for tech support but rather for genuine, broadly applicable improvements to the instructions:

[**https://github.com/talkpython/installing-python**](https://github.com/talkpython/installing-python)
