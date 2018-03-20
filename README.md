The following instructions detail how to install ROOT 6 with an external Anaconda Python 3.6 library. The operating system being used for this installation is Ubuntu 18.

From a fresh Ubuntu 18 install, download the following programs.

[Cern Root 6: ](https://root.cern.ch/content/release-60806) || Download the Source

[Anaconda (SciPy):](https://www.anaconda.com/download/#linux) || 64-Bit (x86) Installer

## Anaconda
| Command  | Info |
| ------------- | ------------- |
| cd /Downloads  | Navigate to the downloads directory  |
| bash Anaconda3-5.0.0.1-Linux-x86_64.sh  | Installs the downloaded Anaconda3  |

## Exporting Python
At the end of the install process you will be prompted asking if you 
want to append the .bashrc with the python path, choose yes. If you do not 
see this option then follow the following commands. 

| Command  | Info |
| ------------- | ------------- |
| gedit .bashrc  | Opens the bashrc in gedit  |
| export PATH=”/home/_PCNAME_/anaconda3/bin:$PATH”  | Installs the downloaded Anaconda3  |
| | Save bashrc file|

## ROOT 6

The following steps detail how root was installed on the SOC computer Columbia using the external python library. From a blank terminal follow the steps below.

| Command  | Info |
| ------------- | ------------- |
| cd /Downloads  | Navigate to the downloads directory  |
| tar -xzf Root_v6.08.06.source.tar.gz  | Un-tar the root download  |
| cd root-6.08.06| Navigate to the un-tared root directory|
| ./configure enable-python –with-python=/home/_PCNAME_/anaconda3/bin/python3.6 –with-python-incdir=/home/_PCNAME_/anaconda3/include/python3.6m –with-python-libdir=/home/_PCNAME_/lib --all| This configures the root build to use the external python, python library, and the included header files|
| gedit config.status | You should see the command that you executed above included in the status, this should be a check, save once confirmed|
| cd| Navigate to your home directory|
| mkdir root6| Make a build directory named root6 |
| cd root6 | Navigates to the root6 directory |
| cmake ../Downloads/root-6.08.06| Makes the root files to the new directory|
| cmake –build .| Builds the root files in the new directory|

##  Exporting Root Libraries / Pointing to Python

| Command  | Info |
| ------------- | ------------- |
| gedit .bashrc  | Opens the bashrc in gedit  |
| #ROOT
export PATH=”/home/creamop/root6/bin:$PATH”
export LD_LIBRARY_PATH=”home/creamop/root6/lib:$LD_LIBRARY_PATH”  
export PYTHONPATH=”/home/creamop/root6/lib:$PYTHONPATH”
  | Exports root, its library, and the pythonpath  |
| | Save bashrc file |

