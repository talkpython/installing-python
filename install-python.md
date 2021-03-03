# Installing Python 3

<img src="https://training.talkpython.fm/static/img/cms/nopy-final.jpg" style="border-radius: 10px; display: block;" class="img img-responsive" />

Welcome soon to be Python user! Python is one of the easiest programming languages to learn and grow with. But there are a few bumps right at the beginning. **One of these bumps is to make sure you have Python installed** and that it's a sufficiently new version (generally 3.6+ is solid these days).

Because how you install and verify Python varies by operating system, we've put together this short guide. It's goal is to give you exposure to the various ways on your operating system to **install and maintain Python in a concise and no-nonsense manner**. So with out further ado, let's get you setup! 

## Step 1. Go To Your Operating System

As mentioned above, how you verify Python and subsequently install it is specific to the operating system. So jump to:

* [**Windows**](#windows)
* [**macOS**](#macos)
* [**Linux**](#linux) 

<a id="windows" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## Windows

### Step 2. Do you have Python? Let's check

To determine if you have Python installed, open the [**command prompt**](https://www.lifewire.com/how-to-open-command-prompt-2618089) or (preferred) install [**new Windows Terminal**](https://devblogs.microsoft.com/commandline/introducing-windows-terminal/) from the [**Microsoft Store**](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab).

Verify you have Python, in the command prompt / terminal, type **python -V** (capital V):

```
C:\users\username\> python -V
```

The output should be one of the following (*version numbers will vary*). **C:\users\username\> is not typed** - Windows displays this as part of the terminal UI.

#### Success, you have Python

```
C:\users\username\> python -V
Python 3.9.2
```

If you see this and the reported version number is sufficently high (often 3.6 or higher), **you are good to go**. 

#### Uh oh, your Python is badly outdated

```
C:\users\username\> python -V
Python 2.7.18
```

If you have `Python 2.*`, then you are using an outdated version of Python. [**Since 2020, Python 2 has gone entirely unsupported**](https://stackoverflow.blog/2020/04/23/the-final-python-2-release-marks-the-end-of-an-era/) and should not be used. **You will need to continue below to install Python 3**.

#### Ooops, you do NOT have Python

```
C:\users\username\> python -V
'python' is not recognized as a command or program.
```

Looks like you do not have Python at all. **You will need to continue below to install Python 3**. Note that the error message may be slightly different for **Windows Terminal**: *The term python is not recognized as a cmdlet, function, or operable program*.

#### Ooops, you still do NOT have Python

```
C:\users\username\> python -V
Python was not found; run without arguments to install from the Windows Store...
```

Looks like you do not have Python at all. **You will need to continue below to install Python 3**. When you see this specific error message, it means that Python is not installed. What is running is a shim program meant to help you install Python 3 from the Windows Store (one option below). You can select this option by simplying typing `python` and following along in the UI.


### Step 3. You need Python, install it on Windows

So you need to install a new version of Python on your Windows machine. There are a variety of options for doing so. We'll run you through them, but **if you are uncertain which one to get, just use the official installer**. Keep in mind that no matter how you install Python, **you will likely need to close and reopen your terminal/command prompt for any changes to take effect**.

- **Python Official Installer** << recommended
- Windows Store
- Chocolatey Package Manager for Windows
- Anaconda Distribution

#### << **Python Official Installer on Windows** >>

The Python official installer can be found on **[python.org](http://python.org)**. 

**Pros**

* It's the primary way the Python Software Foundation delivers Python to users
* The installer is supported by core developers working at Microsoft

**Cons**

* You will not be notified of possible updates
* There is no mechanism to have a new version automatically replace the installed version

**Install steps - Windows official installer**:

1. Visit the **[downloads page for Windows at python.org](https://www.python.org/downloads/windows/)**
2. Find the section entitled **Stable Releases** 
3. Download the MSI installer under the **Download Windows installer (64-bit)** link
4. Run the installer - **be sure to check the "add python to my path" option**
5. Close all terminal and command prompt windows
6. Run `python -V` in a new terminal window to verify you have Python now working

#### << **Windows Store version of Python** >>

The Windows Store version of Python is a good option. It's the easiest way to get Python on Windows without administrator permissions. But there are some drawbacks too.

**Pros**

* Easiest way to get Python on Windows **without administrator permissions**
* Will keep Python up-to-date automatically within a release version (3.9 updates but not 3.9->3.10)
* Maintained by the core developers who work at Microsoft

**Cons**

* Does have some minor permission restrictions that apply to all Windows Store apps which can affect your development options

**Install steps - Microsoft Store Python**:

1. Open the Microsoft Store on Windows
2. Search for Python
3. Find the latest version of Python from Microsoft (currently lists 3.7, 3.8, and [**3.9**](https://www.microsoft.com/en-us/p/python-39/9p7qfqmjrfp7?activetab=pivot:overviewtab))
4. Install from the Microsoft Store
5. Close all terminal and command prompt windows
6. Run `python -V` in a new terminal window to verify you have Python now working


#### << **Chocolatey Package Manager for Windows** >>

Chocolatey is a [package manager](https://en.wikipedia.org/wiki/Package_manager): software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner. If you're comfortable using package managers, then this is a good option for you because you can continually update and maintain Python on your system.

**Pros**

* Will keep Python up-to-date on your system as long as you periodically run the upgrade command
* Will update across versions (e.g. 3.9 -> 3.10)
* Can inform you of pending upgrade if upgrade command is run

**Cons**

* Complex to use
* Must run as administrator
* Requires separate install of chocolatey itself

**Install steps - Chocolatey package manager on Windows**

1. Install Chacolatey - [**steps here**](https://docs.chocolatey.org/en-us/choco/setup)
2. Open an **[administrator command prompt](https://www.howtogeek.com/194041/how-to-open-the-command-prompt-as-administrator-in-windows-8.1/)**
3. Install the latest Python: `choco install python`
4. Peridocially check for a new release: Open admin command prompt and run `choco upgrade python`
5. Close all terminal and command prompt windows
6. Run `python -V` in a new terminal window to verify you have Python now working


#### << **Anaconda distribution on Windows** >>

[Anaconda is a distribution of Python](https://www.anaconda.com/products/individual) that packages many of the common data science packages pre-configured for your system. It is a good option for data scientists.

**Pros**

* Many packages and libraries are pre-installed
* Good for data science tooling in Python

**Cons**

* Generally uses [conda environements](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) rather than [Python's virtual environments](https://www.geeksforgeeks.org/python-virtual-environment/) - this can lead to a mismatch in instructions when Anaconda is not the primary tool used.
* Packages available here often lag behind in release schedule from PyPI / pip
* Often one whole version behind on Python (e.g. 3.8 rather than 3.9)

**Install steps - Anaconda distribution on Windows**

1. [Download the Windows installer](https://www.anaconda.com/products/individual#)
2. Run the installer, add Python to path if asked
3. Close all terminal and command prompt windows
4. Run `python -V` in a new terminal window to verify you have Python now working




<a id="macos" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## macOS

### Step 2. Do you have Python? Let's check

To determine if you have Python installed, open the [**terminal**](https://www.makeuseof.com/open-terminal-on-mac/). Verify you have Python: In the terminal, type **python3 -V** (capital V):

```
$ python3 -V
```

The output should be one of the following (*version numbers will vary*). Do not type **$** - macOS displays this as part of the terminal UI.

#### Success, you have Python

```
$ python3 -V
Python 3.9.2
```

If you see this and the reported version number is sufficently high (often 3.6 or higher), **you are good to go**. 

#### Uh oh, your Python is badly outdated

If `python3` **does NOT run successfully**, but `python` (without the 3) itself does and you see the output:

```
$ python -V
Python 2.7.18
```

If you have `Python 2.*`, then you are using an outdated version of Python. [**Since 2020, Python 2 has gone entirely unsupported**](https://stackoverflow.blog/2020/04/23/the-final-python-2-release-marks-the-end-of-an-era/) and should not be used. **You will need to continue below to install Python 3**.

#### Ooops, you do NOT have Python

```
$ python3 -V
bash: python3: command not found
```

Looks like you do not have Python 3 at all. **You will need to continue below to install Python 3**. Note that the error message is slightly different for different shells.


### Step 3. You need Python, install it on macOS

- **Homebrew** << recommended
- Python Official Installer
- Anaconda distribution


#### << **Homebrew Package Manager for macOS** >>

**[Homebrew](https://brew.sh/)** is a [package manager](https://en.wikipedia.org/wiki/Package_manager): software tools that automates the process of installing, upgrading, configuring, and removing computer programs for a computer's operating system in a consistent manner. If you're comfortable using package managers, then this is a good option for you because you can continually update and maintain Python on your system.

**Pros**

* Will keep Python up-to-date on your system as long as you periodically run the upgrade command
* Will update across versions (e.g. 3.9 -> 3.10)
* Can inform you of pending upgrade if upgrade command is run

**Cons**

* Complex to use
* Requires separate install of homebrew itself

**Install steps - Homebrew package manager on macOS**

1. Install Homebrew - [**steps here**](https://brew.sh/)
2. Open a **[terminal](https://www.makeuseof.com/open-terminal-on-mac/)**
3. Install the latest Python: `brew install python`
4. Peridocially check for a new release: Open terminal and run `brew update` then `brew upgrade`
5. **CAREFUL**: Take careful note of any messages shown - sometimes you must [update your path](https://coolestguidesontheplanet.com/add-shell-path-osx/) (varies by default shell: bash, zsh, etc.) for this version to be located.
5. Close all terminal windows
6. Run `python3 -V` in a new terminal window to verify you have Python now working


#### << **Python Official Installer on macOS** >>

The Python official installer can be found on **[python.org](http://python.org)**. 

**Pros**

* It's the primary way the Python Software Foundation delivers Python to users
* The installer is supported by core developers

**Cons**

* You will not be notified of possible updates
* There is no mechanism to have a new version automatically replace the installed version
* Requires admin permissions

**Install steps - macOS official installer**:

1. Visit the **[downloads page for macOS](https://www.python.org/downloads/mac-osx/)**
2. Find the section entitled **Stable Releases** 
3. Download the PKG installer under the **Download macOS 64-bit universal2 installer** link
4. Run the installer
5. Close all terminal and command prompt windows
6. Run `python3 -V` in a new terminal window to verify you have Python now working


#### << **Anaconda distribution on macOS** >>

[Anaconda is a distribution of Python](https://www.anaconda.com/products/individual) that packages many of the common data science packages pre-configured for your system. It is a good option for data scientists.

**Pros**

* Many packages and libraries are pre-installed
* Good for data science tooling in Python

**Cons**

* Generally uses [conda environements](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) rather than [Python's virtual environments](https://www.geeksforgeeks.org/python-virtual-environment/) - this can lead to a mismatch in instructions when Anaconda is not the primary tool used.
* Packages available here often lag behind in release schedule from PyPI / pip
* Often one whole version behind on Python (e.g. 3.8 rather than 3.9)

**Install steps - Anaconda distribution on Windows**

1. [Download the macOS installer](https://www.anaconda.com/products/individual#)
2. Run the installer, add Python to path if asked
3. Close all terminal and command prompt windows
4. Run `python3 -V` in a new terminal window to verify you have Python now working






<a id="linux" style="margin-bottom: 10px; display: inline-block;"></a>
_________________________

## Linux

### Step 2. Do you have Python? Let's check

To determine if you have Python installed, open the [**terminal**](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/). Verify you have Python, in the terminal, type **python3 -V** (capital V):

```
$ python3 -V
```

The output should be one of the following (*version numbers will vary*). Don't type **$** - Linux displays this as part of the terminal UI.

#### Success, you have Python

```
$ python3 -V
Python 3.9.2
```

If you see this and the reported version number is sufficently high (often 3.6 or higher), **you are good to go**. 

#### Uh oh, your Python is badly outdated

If `python3` **does NOT run successfully**, but `python` (without the 3) itself does and you see the output:

```
$ python -V
Python 2.7.18
```

If you have `Python 2.*`, then you are using an outdated version of Python. [**Since 2020, Python 2 has gone entirely unsupported**](https://stackoverflow.blog/2020/04/23/the-final-python-2-release-marks-the-end-of-an-era/) and should not be used. **You will need to continue below to install Python 3**.

#### Ooops, you do NOT have Python

```
$ python3 -V
bash: python3: command not found
```

Looks like you do not have Python 3 at all. **You will need to continue below to install Python 3**. Note that the error message is slightly different for different shells.


### Step 3. You need Python, install it on Linux

- **Package manager** << recommended
- Anaconda
- Compiled from source

Note that **these instructions are for Ubuntu**. With the many variants of Linux, you many need to adjust slightly (e.g. yum vs. apt)


#### << **Built-in Package Manager for Ubuntu** >>

Ubuntu manages it's installed software using **[apt](https://ubuntu.com/server/docs/package-management)**. This is a good way to install and manage Python 3 on your system.

**Pros**

* Will keep Python up-to-date on your system as long as you periodically run the upgrade command
* Will update across versions (e.g. 3.9 -> 3.10)
* Can inform you of pending upgrade if upgrade command is run

**Cons**

* Requires root permissions
* Often lags badly behind the latest version (currently about 1.5 years behind)

**Install steps - apt package manager on Ubuntu**

1. Open a **[terminal](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/)**
2. Update the package sources: `sudo apt update`
3. Upgrade currently installed software: `sudo apt upgrade`
4. Install the latest Python 3: `sudo apt install build-essential libssl-dev libffi-dev python3-dev`
4. Make sure we have pip as part of our Python: `sudo apt install python3-pip`
5. Close all terminal windows
6. Run `python3 -V` in a new terminal window to verify you have Python now working



#### << **Anaconda distribution on Ubuntu** >>

[Anaconda is a distribution of Python](https://www.anaconda.com/products/individual) that packages many of the common data science packages pre-configured for your system. It is a good option for data scientists.

**Pros**

* Many packages and libraries are pre-installed
* Good for data science tooling in Python

**Cons**

* Generally uses [conda environements](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) rather than [Python's virtual environments](https://www.geeksforgeeks.org/python-virtual-environment/) - this can lead to a mismatch in instructions when Anaconda is not the primary tool used.
* Packages available here often lag behind in release schedule from PyPI / pip
* Often one whole version behind on Python (e.g. 3.8 rather than 3.9)

**Install steps - Anaconda distribution on Windows**

1. [Download the Linux installer](https://www.anaconda.com/products/individual#)
2. Run the installer, add Python to path if asked
3. Close all terminal and command prompt windows
4. Run `python3 -V` in a new terminal window to verify you have Python now working




#### << **Building python from source on Ubuntu** >>

While we would not generally recommend building Python 3 from source, if you need the very latest on your system, often this is one of the few options available. 

**Pros**

* You'll have the very latest Python you've gotten from source (potentially even pre-release versions)

**Cons**

* Complicated and fraught with pitfalls
* Can require root permissions for additional build libraries


**Install steps - Building python from source on Ubuntu**

1. Open a **[terminal](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/)**
2. Ensure your package listings and software are up-to-date: `sudo apt-get update`
3. Install the build tools: `sudo apt-get install -y build-essential checkinstall`
4. Add additional libraries needed by Python to build: `apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev libffi-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev`
5. Change into the src directory: `cd /usr/src`
6. Get the latest source from [python.org/downloads/source](https://www.python.org/downloads/source/) and wget it locally, e.g.: `sudo wget https://www.python.org/ftp/python/3.9.2/Python-3.9.2.tgz`
7. Decompress it (varies by version):  `sudo tar xzf Python-3.9.2.tgz`
8. Change into the created directory (varies by version): `cd Python-3.9.2`
9. Prepare it for compilation: `sudo ./configure --enable-optimizations`
10. Compile it without modifying system Python: `sudo make altinstall`
11. Verify this version was built (varies by version): `python3.9 --version`
12. Use `python3.9` instead of `python` or `python3` commands
13. Consider creating an [alias](https://www.howtogeek.com/73768/how-to-use-aliases-to-customize-ubuntu-commands/) of python3.9 to python in your shell profile.

There is a [nice write up of this procedure over here](https://towardsdatascience.com/building-python-from-source-on-ubuntu-20-04-2ed29eec152b).


-------------------------------

## Corrections and improvements

If you find a problem or have a suggestion to make this page better, please visit the GitHub repository here. Note that this is not intended for tech support but rather for genuine, broadly applicable improvements to the instructions:

[**https://github.com/talkpython/installing-python**](https://github.com/talkpython/installing-python)