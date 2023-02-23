## Install in mac osx

### Install brew 
To install Homebrew, open Terminal or your favorite OS X terminal emulator and run
```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
The script will explain what changes it will make and prompt you before the installation begins. Once you’ve installed Homebrew, insert the Homebrew directory at the top of your PATH environment variable. You can do this by adding the following line at the bottom of your ~/.profile file
```
export PATH="/usr/local/opt/python/libexec/bin:$PATH"
```
If you have OS X 10.12 (Sierra) or older use this line instead
```
export PATH=/usr/local/bin:/usr/local/sbin:$PATH
```
Now, we can install Python 3:
```
$ brew install python
```

### Working with Python 3
At this point, you have the system Python 2.7 available, potentially the Homebrew version of Python 2 installed, and the Homebrew version of Python 3 as well.
```
$ python 
```
will launch the Homebrew-installed Python 3 interpreter.
```
$ python2 
```
will launch the Homebrew-installed Python 2 interpreter (if any).
```
$ python3 
```
will launch the Homebrew-installed Python 3 interpreter.

If the Homebrew version of Python 2 is installed then pip2 will point to Python 2. If the Homebrew version of Python 3 is installed then pip will point to Python 3.

The rest of the guide will assume that python references Python 3.

Do I have a Python 3 installed?
``` 
$ python --version
Python 3.7.1 # Success! 
```
### Installing/Upgrading PIP

Download pip via the get-pip.py script.
Download pip by running the following command:
```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
```
The curl command allows you to specify a direct download link. Use the -o option to set the name of the downloaded file.

Install the downloaded package by running:
```
python3 get-pip.py
```
If pip is already installed:
```
pip install --upgrade pip
```
If you get an error about the pip command not being found, the easiest thing to do is use your Python interpreter:
```
python -m pip install --upgrade pip
```
Some installations will also install an alias called pip3:
```
pip3 install --upgrade pip
```

### Installing Pipenv
Pipenv is a dependency manager for Python projects. If you’re familiar with Node.js’ npm or Ruby’s bundler, it is similar in spirit to those tools. While pip can install Python packages, Pipenv is recommended as it’s a higher-level tool that simplifies dependency management for common use cases.

Use pip to install Pipenv:
```
$ pip install --user pipenv
```
Installing packages for your project
Pipenv manages dependencies on a per-project basis. To install packages, change into your project’s directory (or just an empty directory for this tutorial) and run:
```
$ cd project_folder
$ pipenv install "pythonlib"
```
Pipenv will install the excellent Requests library and create a Pipfile for you in your project’s directory. The Pipfile is used to track which dependencies your project needs in case you need to re-install them, such as when you share your project with others.

Then you can run this script using pipenv run:
```
$ pipenv run python main.py
```

### Installing virtualenv
virtualenv is a tool to create isolated Python environments. virtualenv creates a folder which contains all the necessary executables to use the packages that a Python project would need.

It can be used standalone, in place of Pipenv.

Install virtualenv via pip:
```
$ pip install virtualenv
```
Test your installation:
```
$ virtualenv --version
```
Basic Usage
Create a virtual environment for a project:
```
$ cd project_folder
$ virtualenv venv
```
virtualenv venv will create a folder in the current directory which will contain the Python executable files, and a copy of the pip library which you can use to install other packages. The name of the virtual environment (in this case, it was venv) can be anything; omitting the name will place the files in the current directory instead.

This creates a copy of Python in whichever directory you ran the command in, placing it in a folder named venv.

You can also use the Python interpreter of your choice (like python2.7).
```
$ virtualenv -p /usr/bin/python2.7 venv
```
or change the interpreter globally with an env variable in ~/.bashrc:
```
$ export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3.7
```
To begin using the virtual environment, it needs to be activated:
```
$ source venv/bin/activate
```
The name of the current virtual environment will now appear on the left of the prompt (e.g. (venv)Your-Computer:project_folder UserName$) to let you know that it’s active. From now on, any package that you install using pip will be placed in the venv folder, isolated from the global Python installation.

Install packages using the pip command:
```
$ pip install "python_lib"
```
If you are done working in the virtual environment for the moment, you can deactivate it:
```
$ deactivate
```
This puts you back to the system’s default Python interpreter with all its installed libraries.

To delete a virtual environment, just delete its folder. (In this case, it would be rm -rf venv.)

In order to keep your environment consistent, it’s a good idea to “freeze” the current state of the environment packages. To do this, run:
```
$ pip freeze > requirements.txt
```
This will create a requirements.txt file, which contains a simple list of all the packages in the current environment, and their respective versions. You can see the list of installed packages without the requirements format using pip list. Later it will be easier for a different developer (or you, if you need to re-create the environment) to install the same packages using the same versions:
```
$ pip install -r requirements.txt
```
This can help ensure consistency across installations, across deployments, and across developers.

### Installing virtualenvwrapper
virtualenvwrapper provides a set of commands which makes working with virtual environments much more pleasant. It also places all your virtual environments in one place.

To install (make sure virtualenv is already installed):
```
$ pip install virtualenvwrapper
$ export WORKON_HOME=~/Envs
$ source /usr/local/bin/virtualenvwrapper.sh
```
(Full virtualenvwrapper install instructions.)

For Windows, you can use the virtualenvwrapper-win.

To install (make sure virtualenv is already installed):
```
$ pip install virtualenvwrapper
```
In Windows, the default path for WORKON_HOME is %USERPROFILE%\Envs

Basic Usage
Create a virtual environment:
```
$ mkvirtualenv project_folder
```
This creates the project_folder folder inside ~/Envs.

Work on a virtual environment:
```
$ workon project_folder
```
Alternatively, you can make a project, which creates the virtual environment, and also a project directory inside $WORKON_HOME, which is cd-ed into when you workon project_folder.
```
$ mkproject project_folder
```
virtualenvwrapper provides tab-completion on environment names. It really helps when you have a lot of environments and have trouble remembering their names.

workon also deactivates whatever environment you are currently in, so you can quickly switch between environments.

Deactivating is still the same:
```
$ deactivate
```
To delete:
```
$ rmvirtualenv venv
```

### Manage multiple versions of Python
Install pyenv - but before that install dependencies 
```
brew install openssl readline sqlite3 xz zlib
```
Install pyenv
```
curl https://pyenv.run | bash
```
Update your bashrc with pyenv path 
```
Load pyenv automatically by adding
the following to ~/.bashrc:

export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
### Using pyenv to Install Python
Now that you have pyenv installed, installing Python is the next step. You have many versions of Python to choose from. If you wanted to see all the available CPython 3.6 through 3.8, you can do this:
```
$ pyenv install --list | grep " 3\.[678]"
```
If you want to see all the versions, you can do the following:
```
$ pyenv install --list
```
Once you find the version you want, you can install it with a single command:
```
$ pyenv install -v 3.7.2
```
### Check Installation Location
As mentioned before, pyenv works by building Python from source. Each version that you have installed is located nicely in your pyenv root directory:
```
$ ls ~/.pyenv/versions/
2.7.15  3.6.8  3.8-dev
```
All of your versions will be located here. This is handy because removing these versions is trivial:
```
$ rm -rf ~/.pyenv/versions/2.7.15
```
Of course pyenv also provides a command to uninstall a particular Python version:
```
$ pyenv uninstall 2.7.15
```
Now that you’ve installed a couple of different Python versions, let’s see some basics on how to use them. First, check what versions of Python you have available:
```
$ pyenv versions
* system (set by /home/realpython/.pyenv/version)
  2.7.15
  3.6.8
  3.8-dev
  ```
The * indicates that the system Python version is active currently. You’ll also notice that this is set by a file in your root pyenv directory. This means that, by default, you are still using your system Python:
```
$ python -V
Python 2.7.12
```
If you try to confirm this using which, you’ll see this:
```
$ which python
/home/user/.pyenv/shims/python
```
This might be surprising, but this is how pyenv works. pyenv inserts itself into your PATH and from your OS’s perspective is the executable that is getting called. If you want to see the actual path, you can run the following:
```
$ pyenv which python
/usr/bin/python
```
If, for example, you wanted to use version 2.7.15, then you can use the global command:
```
$ pyenv global 2.7.15
$ python -V
Python 2.7.15
```
Check default version of python
```
$ pyenv versions
  system
* 2.7.15 (set by /home/realpython/.pyenv/version)
  3.6.8
  3.8-dev
```
If you ever want to go back to the system version of Python as the default, you can run this:
```
$ pyenv global system
$ python -V
```

### Install Jupyterlab or Jupyter Notebook 
#### JupyterLab
Install JupyterLab with pip:
```
pip install jupyterlab
```
Note: If you install JupyterLab with conda or mamba, we recommend using the conda-forge channel.

Once installed, launch JupyterLab with:
```
jupyter-lab
```
#### Jupyter Notebook
Install the classic Jupyter Notebook with:
```
pip install notebook
```
To run the notebook:
```
jupyter notebook
```

