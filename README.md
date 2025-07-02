# Introduction to computing with Python for engineering and scientific applications

These Jupyter notebooks provide a self-study introduction to computing
with Python. They have been developed for the computing course in Part
IA (Michaelmas Term) of the Engineering Tripos at University of
Cambridge. This is a first computing course for undergraduate students.

The notebooks can be freely used, shared and modified. See the copyright
and license notice below.

## Getting Set Up

### Pre-requisite - Command Line

You will need to understand how to run commands from a command line.  Please
read [this tutorial](https://ubuntu.com/tutorials/command-line-for-beginners).

### Pre-requisite - Python

There are many ways to install Python.  Below we provide one possible method.

In the DPO:
- Boot into linux.  It's set up and ready to go!

Ubuntu:
- It’s fairly likely you will already have Python installed, but it might only have the command python3 available.  In order to allow python3 venv’s and alias python to python3, a full set of packages to install might be: ```sudo apt install python3 python3-venv python-is-python3```

MacOS:
- Install Homebrew: https://brew.sh/
- Run:
    ```brew install python```

Windows:
- We recommend using [WSL (Windows Subsystem for Linux)](https://learn.microsoft.com/en-us/windows/wsl/install).
During your future career as an engineer, you will need to be comfortable using a
Linux/Unix style terminal.  WSL allows you to do this from a Windows installation,
supported by Microsoft.
- In the Windows Search bar, search for "Turn Windows feature on or off" and open it.
- Enable the "Hyper-V", "Virtual Machine Platform" and "Windows Subsystem for Linux" boxes.
- Click OK and restart your PC when prompted.
- In the Windows search bad, search for ```cmd```, click “Run as administrator”
- Click “Yes”, when it checks this is ok
- Run:
    ```wsl --install```
- Follow the on screen instructions to set up a username and a password.
- Close the Windows command terminal.
- Launch a wsl terminal by typing ```wsl``` into the Windows search bar and run it (remember this step - you will run it everytime you need to start a new wsl terminal).
- To install the relevant dependencies:
    ```
    sudo apt-get update
    sudo apt-get install python3 python3-venv python-is-python3 python3-pip
    ```
    *nb* the last command will install a lot of dependencies.  Confirm by hitting return ([Y/n] means enter "y" for "yes" and "n" for "no", with "Y"=yes as the default answer.)



### Pre-requisite - Git

In the DPO:
- Boot into linux.  It's set up and ready to go!

Ubuntu:
- Already installed by default from Ubuntu 24.04

MacOs:
- (Requires Homebrew, see above.)  Run:
    ```brew install git```

Windows:
 - If using WSL, this will already be installed by default.

### Setting up Git

You will need to use git to obtain the relevant notebooks.  You will use git very often going forwards, this is a good time to learn how to use it!  For this course, get into the habit of saving your notebook and _pushing_ the change.

Make an account on [GitHub](https://github.com/), perhaps using your CRSid as a username.

You may wish to consider using SSH Keys to allow for easy command line access to GitHub, see: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent and https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
(Remember on Windows if using WSL, to follow the Linux instructions!)

Read and boomark this basic introduction to git: https://rogerdudler.github.io/git-guide/

### Get the Notebooks

You will need to make your own *private* copy of the notebooks, by following these instructions *once*:
- Create a new repo and mark it *private*: https://github.com/new
    e.g. named PartIA-Computing-Michaelmas_CSRid (replacing the CRSid with yours.)
- Clone the code locally:
    ```
    git clone --bare https://github.com/CambridgeEngineering/PartIA-Computing-Michaelmas
    ```
- Push a copy of this repo to your private repo (replace _username_ and the repo name below, as required):
    ```
    cd PartIA-Computing-Michaelmas.git
    ```
    - If you set up ssh-keys:
        ```
        git push --mirror git@github.com:username/PartIA-Computing-Michaelmas_CSRid
        ```
    - Otherwise:
        ```
        git push --mirror https://github.com/username/PartIA-Computing-Michaelmas_CSRid
        ```
- Remove the original version to avoid confusion:
    ```
    cd ..
    rm -rf PartIA-Computing-Michaelmas.git
    ```
- _Clone_ your private copy on whichever device you need it (e.g. once in the DPO and once on your laptop/college PC), as follows:
    - If you set up ssh-keys:
        ```
        git clone git@github.com:username/PartIA-Computing-Michaelmas_CSRid
        ```
    - Otherwise:
        ```
        git clone https://github.com/username/PartIA-Computing-Michaelmas_CSRid
        ```


Remember to ensure you are update with any commits before editting (putting any local, unpushed commits to the top):
```
git pull --rebase
```

### Python Virtual Environment

A Python virtual environment, using the venv module, is a lightweight, compartmentalised Python environment with its own independent set of packages.  It can be useful in environments whereby you don’t have the ability or desire to add packages globally (e.g. where you might need root access) or for testing to check you have correctly listed your dependencies.

Creating a virtual environment (once per venv instance):
```
python -m venv venv
```
*nb* The second "venv" is the name of the venv, it can be whatever you like

Activating a virtual environment (every time you need to use the venv):
- WSL/Linux/MacOs (bash/zsh):
    ```
    source venv/bin/activate
    ```
    *nb* where "venv" is the name of the venv you chose above.

- Windows (cmd.exe - *nb* instruction to install not provided above):
    ```
    venv\Scripts\activate.bat
    ```
    *nb* where "venv" is the name of the venv you chose above.

Note you should see ```(venv)``` (where venv is the name you chose) to the left of your command prompt, so you know your venv has been activated.

### Python Requirements:

You will need several Python packages installed.  You can use pip to achieve this within you're virtual environment:
```
pip install jupyterlab matplotlib numpy python-dateutil ipywidgets scipy numba requests pytest flake8
```

### Launch Jupyter Lab

Within your Python virtual environment:
```
jupyter-lab
```

Note the output log, it'll give you a locally hosted web address to load in your browser (on some systems it will open the browser for you automatically).

Under "Notebook" click "Python 3 (ipykernel)", then from the file browser on the left, find the .ipynb file you'd like to work with.  Remember to keep saving your changes and then commit and push them to git.


## Getting Started

Each notebook covers a topic, with a number of exercises for completion
at the end of each notebook. Start with the notebook 00 Part IA Michaelmas
Term computing. Model solutions to the exercises are available - contact [Flavia Mancini](<fm456@cam.ac.uk>) and [Jon Bonsor-Matthews](<jpm66@cam.ac.uk>) to request the solutions.


## Accompanying exercises

For each notebook there are a set of exercises in the directory
[Exercises](./Exercises/) for completion at end the of each Activity
notebook.


## Feedback and corrections

These notebooks are maintained at
https://github.com/CambridgeEngineering/PartIA-Computing-Michaelmas.
Please report suggestions or errors at:

https://github.com/CambridgeEngineering/PartIA-Computing-Michaelmas/issues


## Author

These notebooks were developed by Garth N. Wells.


## Acknowledgements

Valuable feedback during the development of the notebooks was provided
by Quang T. Ha, Hugo Hadfield, Tim Love, Chris Richardson and Joanna
Stadnik.


## License and copyright

All material is copyright of Garth N. Wells (<gnw20@cam.ac.uk>).

All text is made available under the Creative Commons
Attribution-ShareAlike 4.0 International Public License
(https://creativecommons.org/licenses/by-sa/4.0/legalcode).

All computer code is released under the MIT license.

The MIT License (MIT)
Copyright (c) 2016-2022 Garth N. Wells

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
