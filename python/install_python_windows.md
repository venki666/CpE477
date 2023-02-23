## Install python[3] (navie) in windows

Check if you have python already installed. To check if you already have Python on your Windows machine,
first open a command-line application, such as PowerShell.

```
Press the Win key.
Type PowerShell.
Press Enter.
```

With the command line open, type in the following command and press Enter:
```
C:\> python --version
Python 3.11.1
```

you can find the default installation location of python by using the command
```
C:\> where.exe python
C:\Users\mertz\AppData\Local\Programs\Python\Python37-32\python.exe
```
### Download and install python
For professional developers who need a full-featured Python development environment, installing from the full installer is the right choice. It offers more customization and control over the installation than installing from the Microsoft Store.

You can install from the full installer in two steps.

**Step 1: Download the Full Installer**
Follow these steps to download the full installer:

Open a browser window and navigate to the Python.org Downloads page for Windows.

Under the “Python Releases for Windows” heading, click the link for the Latest Python 3 Release - Python 3.x.x. As of this writing, the latest version was Python 3.11.1.

Scroll to the bottom and select either Windows x86-64 executable installer for 64-bit or Windows x86 executable installer for 32-bit.

If you aren’t sure whether to select the 32-bit or the 64-bit installer, then you can expand the box below to help you decide.
When the installer is finished downloading, move on to the next step.

**Step 2: Run the Installer**
Once you’ve chosen and downloaded an installer, run it by double-clicking on the downloaded file. A dialog box like the one below will appear:

<img src="https://files.realpython.com/media/Screen_Shot_2020-07-16_at_11.19.15_AM.6e62bfc6eede.png" width=300 align=center>

There are four things to notice about this dialog box:

* The default install path is in the AppData/ directory of the current Windows user.

* The Customize installation button can be used to customize the installation location and which additional features get installed, including pip and IDLE.

* The Install launcher for all users (recommended) checkbox is checked default. This means every user on the machine will have access to the py.exe launcher. You can uncheck this box to restrict Python to the current Windows user.

* The Add Python 3.11 to PATH checkbox is unchecked by default. There are several reasons that you might not want Python on PATH, so make sure you understand the implications before you check this box.

The full installer gives you total control over the installation process.

**Step 3: Verify Pip Was Installed**
If you opted to install an older version of Python, it is possible that it did not come with Pip preinstalled. Pip is a powerful package management system for Python software packages. Thus, make sure that you have it installed.

We recommend using Pip for most Python packages, especially when working in virtual environments.

To verify whether Pip was installed:

* Open the Start menu and type "cmd."
* Select the Command Prompt application.
* Enter pip -V in the console. If Pip was installed successfully, you should see the following output:

<img src="https://phoenixnap.com/kb/wp-content/uploads/2021/04/verify-pip.png" width=300 align=center>

**Step 4: Add Python Path to Environment Variables**
We recommend you go through this step if your version of the Python installer does not include the Add Python to PATH checkbox or if you have not selected that option.

Setting up the Python path to system variables alleviates the need for using full paths. It instructs Windows to look through all the PATH folders for “python” and find the install folder that contains the python.exe file.

* Open the Start menu and start the Run app.

* Type sysdm.cpl and click OK. This opens the System Properties window.

* Navigate to the Advanced tab and select Environment Variables.

* Under System Variables, find and select the Path variable.

* Click Edit.

* Select the Variable value field. Add the path to the python.exe file preceded with a semicolon (;). For example, in the image below, we have added ";C:\Python34."

**Step 7: Install virtualnv**
You have Python, and you have Pip to manage packages. Now, you need one last software package - virtualnv. Virtualnv enables you to create isolated local virtual environments for your Python projects.

Why use virtualnv?

Python software packages are installed system-wide by default. Consequently, whenever a single project-specific package is changed, it changes for all your Python projects. You would want to avoid this, and having separate virtual environments for each project is the easiest solution.

To install virtualnv:

* Open the Start menu and type "cmd."

* Select the Command Prompt application.

* Type the following pip command in the console:

C:\Users\Username> pip install virtualenv

Upon completion, virtualnv is installed on your system.

To create a virtual environment use the command:
```
virtualenv -p python3 envname
```
where envname is your project name. If we name the project “testproject” we get this line:
```
virtualenv -p python3 testproject
```
This will create the folder virtualenv with these sub directories: bin, include, lib and share.

To load your virtual environment type
```
cd testproject
bin/activate
```
Your virtual environment is now activated.
The shell will show the current virtual environment is loaded.

To return to the normal environment, type
```
deactivate
```
