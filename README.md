# PythonVirtualEnvironments

## Python Setup on Mac 

Install Python 3 on Mac OS X

This short tutorial will show you how to properly install Python 3 on a Mac OS X computer. 
There are multiple ways to install Python 3, including a download from the official Python site, 
however I strongly recommend instead using a package manager like Homebrew to manage all your dependencies going forward. 
It will make your life a lot simpler.

Confirm your Python version
Although Python 2 is installed by default on Apple computers, Python 3 is not. 
You can confirm this by typing in Terminal python --version and hitting Enter:

$ python --version
Python 2.7.15
To check if Python 3 is already installed try running the command python3 --version.
Most likely you’ll see an error message, but it’s worth checking. Even if you have a version of Python 3,
we want to be on the most recent release, which is 3.7.0 at this point in 2018.

Install Xcode and Homebrew
We will use the package manager Homebrew to install Python 3.
Homebrew depends on Apple’s Xcode package, so run the following command to install it:

$ xcode-select --install
Click through all the confirmation commands 
(Xcode is a large program so this might take a while to install depending on your internet connection).

Next, install Homebrew:

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
Note: You can also find this command on the homepage of the Homebrew website. 
It’s easiest to copy and paste since it’s a long command.

To confirm Homebrew installed correctly, run this command:

```sh
$ brew doctor
```

Your system is ready to brew.
Install Python 3
To install the latest version of Python, run the following command:

```sh
$ brew install python3
```

Now let’s confirm which version was installed:

```sh
$ python3 --version
Python 3.7.0
```

To open a Python 3 shell from the command line type python3:

```sh
$ python3
Python 3.7.0 (default, Jun 29 2018, 20:13:13)
[Clang 9.1.0 (clang-902.0.39.2)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
When you want to exit, type exit() and then Return or Ctrl-D (the Control and D key at the same time).
```

Note you can still run Python shells with Python 2 by simply typing python:

```sh
$ python
Python 2.7.15 (default, Jun 17 2018, 12:46:58)
[GCC 4.2.1 Compatible Apple LLVM 9.1.0 (clang-902.0.39.2)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

Bonus: Virtual Environments
You should always use a virtual environment for your Python projects. 
A virtual environment is a way to create an isolated space so you can
for example, run Python 2.7 for one project and Python 3.7 for another on the same computer.
We can use the built-in venv module for this.

It’s a best practice to keep all your virtualenvs in one place, 
for example .virtualenvs/ in your home directory. Let’s create that directory:

```sh
$ mkdir ~/.virtualenvs
```

Now create a new virtual environment called myvenv by running:

```sh
$ python3 -m venv ~/.virtualenvs/myvenv
```

Because we used python3 here our virtual environment knows that
when we type python for a command we mean Python 3 not Python 2.
In order to activate this virtual environment, so we can use it, we must also run the following command:

```sh
$ source ~/.virtualenvs/myvenv/bin/activate
(myvenv) $
```

Note that while the environment is active, you will see its name in parentheses. 
Software packages we install now will only be available within this virtual environment.
You can use the command pip freeze to see all installed software within a virtual environment.

To stop using a virtual environment, either close the Terminal window or enter deactivate:

```sh
(myvenv) $ deactivate
$
```
