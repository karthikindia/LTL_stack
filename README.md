# LTL_stack
This repository consists of three ROS Packages for running correct-by-construction controllers with ROS.
For more information, please visit our [wiki](https://github.com/VerifiableRobotics/LTL_stack/wiki).


=== License ===

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

Installation Guide
Step 1: Install Dependencies
Quick Cheat Sheet
Listed here is the bare-minimum software that must be installed for LTLMoP to run.

For a step-by-step guide on how to install these dependencies, please see the next sections.

Programming language environments:
Java Runtime Environment (JRE) and Java Development Kit (JDK)
Python 2.7.x
Python libraries:
wxPython (A cross-platform GUI library)
NumPy and SciPy (Libraries that provide matrix operations and optimization routines)
Polygon (For decomposition and other polygon operations)
Step-by-Step Guide (Windows)
Java may already be installed on your computer; otherwise, see the Java SE Download Page. Be sure you have both the JRE and the JDK (you should be able to successfully run both java and javac from the command prompt).

Note: You may need to manually add the JDK bin/ folder to your system path. On Windows, this can be done from the command-line using the command setx PATH "%PATH%;C:\Program Files\Java\jdkXXXX\bin" where XXXX is the JDK version number. Otherwise, see this page for more information.

For Python, you can use the official Python installer and official wxPython installer along with this repository of library binaries (be sure to choose the packages for your version and architecture of Python).

Alternatively, for 32-bit Windows, the Python(x,y) package is a fairly convenient way to install everything at once (though you may want to disable installation of large unrelated packages like Eclipse).

Note: You may also need to manually add Python to your system path. The procedure is almost identical to the instructions above for adding the Java path, except you will save the path to the Python folder. Python usually places its folder in C:\PythonXX where XX is the version number.

The Polygon library for Python can be installed using the installer from the official website.

Step-by-Step Guide (Mac OS X)
To install dependencies on OS X, you will need to install a package manager.

Homebrew is recommended, and these instructions will assume you are okay with that choice.

If you already have a working Homebrew installation, you should skip to Step 4.
If you already have MacPorts installed, please see the appendix.
To install Homebrew, open up a Terminal window and run: ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"

If you do not have them already, install the Command Line Tools for Xcode from Apple's developer downloads website (free but unfortunately requires Apple registration).

Run brew doctor. If you see a message like "Consider setting your PATH so that /usr/local/bin occurs before /usr/bin", run:

echo export PATH="/usr/local/bin:$PATH" >> ~/.bash_profile
source ~/.bash_profile 
Ensure you have a java compiler. Run javac; if it asks if you want to install, say yes.
brew install git
brew install python. If it complains about having trouble linking, run brew link --overwrite python.
Install Numpy and Scipy:
brew tap samueljohn/python
brew tap homebrew/science
pip-2.7 install nose
brew install numpy scipy
This will take about ten minutes.

brew install wxmac. This will take a while (10-20 minutes).
brew install wxpython
pip install Polygon2
Step-by-Step Guide (Ubuntu)
Java may already be installed on your computer. If so, you should be able to successfully run both java and javac from a terminal, otherwise you can install Java from a terminal with suds apt-get install default-jre and suds apt-get install default-jdk (or from Synaptic package manager, which can be installed from the Ubuntu Software Center).

Most versions of Linux come with Python pre-installed. The necessary Python packages can be installed from the terminal using sudo apt-get install python-numpy python-scipy python-wxtools (or via Synaptic Package Manager, which itself can be installed from the Ubuntu Software Center).

The Polygon library for Python can be installed using pip install Polygon2 (if you need to install pip you can do so with sudo apt-get install python-pip)

Other Optional Dependencies
This section lists other packages that can be used for extended functionality.

If you will want to be able to view automata as PDFs: install Graphviz.
To perform unrealizable core-finding, LTLMoP currently requires PicoSAT to be installed into an appropriate subdirectory of src/lib/cores, e.g. src/lib/cores/picosat-954. Be sure to enable trace support (i.e. ./configure --trace). See also Tips for compiling PicoSAT on Windows.
To use OMPL for motion planning, you will need to install it.
If you want to use the ODE simulator ( tested only on Windows and Ubuntu ):
Install pygame, PyOpenGL, and PyODE (see the previous section for library sources)
Install the Open Dynamics Engine (ODE):
Get version 0.8 ( no later versions! ).
If you are installing ODE on Windows, you should download the source package, then navigate to the build directory which is populated with different versions of Visual Studio solution folders named vs200X. Open one of these solutions in Visual Studio and build the solution there. This will install ODE on your system.
Step 2: Download LTLMoP
There are three ways to download a copy of LTLMoP:

For general users:

Direct download: Download an up-to-date copy of the LTLMoP development branch (.zip) from GitHub. After downloading, extract the contents of the .zip file to the desired install directory.
Via Git: You can also use Git to clone the repository by running git clone https://github.com/LTLMoP/LTLMoP.git.
For LTLMoP developers:

This method of installation will automatically set up a LTLMoP development environment for you (including automatically creating a fork on GitHub and checking it out).
First, make sure you have Git installed. If you do not, install it as follows:
Windows: Git for Windows ( Note: Please make sure to leave the default option of core.autocrlf enabled)
Mac OS X: brew install git (or, for MacPorts, sudo port install git-core)
Ubuntu: sudo apt-get install git
Download this install script.
Run the script in Python and the follow the directions.
Windows: Double-click the file.
Mac OS X: In a terminal, run python ~/Downloads/LTLMoP_GitHub_Setup.py (if you have a different default downloads directory, you will need to change the path).
Ubuntu: In a terminal, run python /path/to/downloaded/file.
Warning: On Windows, due to write permissions, LTLMoP does not behave well when installed to the Program Files directory. The recommended install directory is C:\LTLMoP. ￼￼￼￼￼

Step 3: Prepare LTLMoP for first use
Run the dist/setup.py script in the LTLMoP folder.
Windows: Double-click the file.
Mac OS X / Ubuntu: In a terminal, run python ~/LTLMoP/dist/setup.py (if you installed LTLMoP to a different directory, you will need to change the path).
You will be asked whether you want to install SLURP, the optional natural language processing subsystem. It is fairly large, so you can skip this step if you don't plan on using it. You can always come back and run this script again if you change your mind later.
That's it! Now go check out the Tutorial.
