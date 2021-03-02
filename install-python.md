# Installing Python 3

<img src="https://training.talkpython.fm/static/img/cms/nopy-final.jpg" style="border-radius: 10px; display: block;" class="img img-responsive" />

Welcome soon to be Python user! Python is one of the easiest programming languages to learn and grow with. But there are a few bumps right at the beginning. **One of these bumps is to make sure you have Python installed** and that it's a sufficiently new version (generally 3.6+ is solid these days).

Because how you install and verify Python varies by operating system, we've put together this short guide. It's goal is to give you exposure to the various ways on your operating system to **install and maintain Python in a concise and no-nonsense manner**. So with out further ado, let's get you setup! 

## Step 1. Go To Your Operating System

As mentioned above, how you verify Python and subsequently install it is specific to the operating system. So jump to [Windows](#windows), [macOS](#macos), or [Linux](#linux) to continue.

<a id="windows"></a>
_________________________

## Windows

### Step 2. Do you have Python? Let's check

To determine if you have Python installed, open the [**command prompt**](https://www.lifewire.com/how-to-open-command-prompt-2618089) or install (preferred) [**new Windows Terminal**](https://devblogs.microsoft.com/commandline/introducing-windows-terminal/) from the [**Microsoft Store**](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab).

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

Looks like you do not have Python at all. **You will need to continue below to install Python 3**. Note that the error message is slightly different for **Windows Terminal**: *The term python is not recognized as a cmdlet, function, or operable program*.

#### Ooops, you still do NOT have Python

```
C:\users\username\> python -V
Python was not found; run without arguments to install from the Windows Store...
```

Looks like you do not have Python at all. **You will need to continue below to install Python 3**. When you see this specific error message, it means that Python is not installed. What is running is a shim program meant to help you install Python 3 from the Windows Store (one option below). You can select this option by simplying typing `python` and following along in the UI.


### Step 3. You need Python, install it on Windows

So you need to install a new version of Python on your Windows machine. There are a variety of options for doing so. We'll run you through them, but **if you are uncertain which one to get, just use the official installer**. Keep in mind that no matter how you install Python, **you will likely need to close and reopen your terminal/command prompt for any changes to take effect**.

- **Python Official Installer** << default
- Windows Store
- Chocolatey Package Manager for Windows
- Anaconda Distribution

**Python Official Installer on Windows**

The Python official installer can be found on **[python.org](http://python.org)**. 

**Pros**: This is a good option

* It's the primary way the Python Software Foundation delivers Python to users
* The installer is supported by core developers working at Microsoft

**Cons**: There is no autoupdate option. 

* You will not be notified of possible updates
* There is no mechanism to have a new version automatically replace the installed version

**Install steps**:

1. Visit the **[downloads page for Windows](https://www.python.org/downloads/windows/)**
2. Find the section entitled **Stable Releases** 
3. Download the MSI installer under the **Download Windows installer (64-bit)** link
4. Run the installer - **be sure to check the "add python to my path" option**
5. Close all terminal and command prompt windows
6. Run `python -V` in a new terminal window to verify you have Python now working

**Windows Store version of Python**

The Windows Store version of Python is a good option. It's the easiest way to get Python on Windows without administrator permissions. But there are some drawbacks too.

**Pros**: 

* Easiest way to get Python on Windows without administrator permissions
* Will keep Python up-to-date automatically within a release version (3.9 updates but not 3.9->3.10)
* Maintained by the core developers who work at Microsoft

**Cons**:

* Does have some minor permission restrictions that apply to all Windows Store apps which can affect your development options

**Install steps**:

1. Open the Microsoft Store on Windows
2. Search for Python
3. Find the latest version of Python from Microsoft (currently lists 3.7, 3.8, and [3.9](https://www.microsoft.com/en-us/p/python-39/9p7qfqmjrfp7?activetab=pivot:overviewtab))
4. Install from the Microsoft Store
5. Close all terminal and command prompt windows
6. Run `python -V` in a new terminal window to verify you have Python now working


### Step 4. Ensure Python 3 is in the path correctly.

<a id="macos"></a>
_________________________

## macOS

### Step 2. Do you have Python? Let's check

### Step 3. You need Python, install it on macOS

- Homebrew
- Installer
- Anaconda



## Linux

### Step 2. Do you have Python? Let's check

### Step 3. You need Python, install it Linux

- Package manager
- Anaconda
- [From source](Building python from source on Ubuntu 20.04 LTS Focal Fossa)