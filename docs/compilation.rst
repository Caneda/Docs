###########
Compilation
###########

.. note:: This document is aimed to developers and advanced users. If you just want to start working with Caneda on your electronics projects, you may jump right into the :ref:`installation` procedure or the :ref:`gettingstarted` guide.

Caneda source code is hosted by GitHub. For more information, see `Caneda on GitHub`_.

.. _`Caneda on GitHub`: https://github.com/Caneda/Caneda

*********
GNU/Linux
*********

General
=======

This section provides the basic guidelines to compile Caneda in GNU/Linux.

The distribution-specific compilation procedures are detailed later on this document, such as: 

  * :ref:`compilation-stretch`
  * :ref:`compilation-jessie`

.. note:: To obtain the distribution name and release of a particular system, execute ``lsb_release -da`` from a system console.

**Requirements**

The following libraries must be installed on the system in order to compile Caneda:

  * CMake
  * Qt 5
  * Qwt 6.1.2 or later
  
Although the package **Ngspice**  is optional, it is strongly recommended to install it in order to add simulation capabilities to Caneda.
  
**Source Code**

Caneda source code repository can be locally cloned using **git** as follows:

.. code-block:: none

  $ git clone https://github.com/caneda/caneda

.. note:: The default Caneda distribution is *master* (stable). Execute ``git checkout develop`` to compile the *develop* (latest) distribution.

Alternatively, download either `master`_ or `develop`_ tarball from the GitHub repository and unpack it:

.. _`master`:  https://github.com/Caneda/Caneda/tarball/master
.. _`develop`: https://github.com/Caneda/Caneda/tarball/develop
    
.. code-block:: none

  $ tar -xvf Caneda-Caneda-<version>.tar.gz

**Compilation Steps**

Create a new folder ``build`` at the top of Caneda source code structure and change into it:
  
.. code-block:: none

  $ cd caneda
  $ mkdir build
  $ cd build
  
Configure and compile the source package:

.. code-block:: none

  $ cmake ../
  $ make

Finally, install Caneda into the system (requires root privileges):

.. code-block:: none

  # make install
  
**Compiler Options**

Some systems require special options for compilation or linking that CMake does not know about.  
Run ``cmake --help`` for details on some of the pertinent environment variables.

CMake can take initial values for configuration parameters by setting environment variables from the command line. 
Here is an example:

.. code-block:: none

  $ cmake CC=gcc-6 CXX=g++-6 CFLAGS=-O2 LIBS=-lposix ../

**Installation Directory**

By default, ``make install`` will install all the package files in ``/usr/local/bin``, ``/usr/local/man``, etc.  
You can specify an installation prefix other than ``/usr/local`` by giving *cmake* the option ``--prefix=PATH``.

You can specify separate installation prefixes for architecture-specific files and architecture-independent files.  
If you give *cmake* the option ``--exec-prefix=PATH``, the package will use *PATH* as the prefix for installing programs and libraries. Documentation and other data files will still use the regular prefix.

In addition, if you use a non-standard directory layout, you can give options like ``--bindir=PATH`` to specify different values for a particular type of files.


**Files Association**

To associate Caneda file types with the application itself, execute the following command:

.. code-block:: none

  $ update-mime-database /usr/local/share/mime

**Documentation**

Caneda uses **Doxygen** as its code documentation for developers. 
To generate the Doxygen documentation, use the Doxyfile file provided at the source root.

.. _compilation-stretch:

Debian 9 Stretch/Testing
========================

The following instructions to compile Caneda are meant to be executed at the system console.
Consider the prefix ``$`` for non-privileged user commands and the prefix ``#`` for root commands.

Use **aptitude** to install the required/suggested packages:

.. code-block:: none

  # aptitude install git cmake g++ qtbase5-dev libqt5svg5-dev qttools5-dev qttools5-dev-tools ngspice libqwt-qt5-dev 
    
.. note:: The simulation engine **Ngspice** is available at the *non-free* Debian repository. Before trying to install it, edit the file **/etc/apt/sources.list** as **root** and make sure the keyword *non-free* is present in the repository details. For example: ``deb http://ftp.us.debian.org/debian/ stretch main non-free``.

Create a temporary folder and change to it:

.. code-block:: none

  $ cd ~
  $ mkdir temp_caneda
  $ cd temp_caneda
      
Get the latest Caneda *git* snapshot:

.. code-block:: none

  $ git clone https://github.com/caneda/caneda

.. note:: The default Caneda distribution is *master* (stable). Execute ``git checkout develop`` to compile the *develop* (latest) distribution.
    
Alternatively, download either `master`_ or `develop`_ tarball from the GitHub repository and unpack it:

.. _`master`:  https://github.com/Caneda/Caneda/tarball/master
.. _`develop`: https://github.com/Caneda/Caneda/tarball/develop
  
.. code-block:: none

  $ tar -xvf Caneda-Caneda-<version>.tar.gz
    
Create the folder ``build`` at the top of the source code structure and change into it:

.. code-block:: none

  $ cd caneda
  $ mkdir build
  $ cd build
    
Configure the source package and start the compilation process:

.. code-block:: none

  $ cmake ../
  $ make
    
Install Caneda into the system by executing:

.. code-block:: none

  # make install
      
To open Caneda from the Application Launcher, open **Applications** > **Development** and then click on *Caneda*. 

Alternatively, open Caneda from a terminal emulator by executing ``caneda &``.

The temporary folder ``~/temp_caneda`` may be deleted at this point.

.. _compilation-jessie:

Debian 8 Jessie/Stable
======================

The following instructions to compile Caneda are meant to be executed at the system console.
Consider the prefix ``$`` for non-privileged user commands and the prefix ``#`` for root commands.

Use **aptitude** to install the required/suggested packages:

.. code-block:: none

  # aptitude install git cmake g++ qtbase5-dev libqt5svg5-dev qttools5-dev qttools5-dev-tools ngspice

.. note:: The simulation engine **Ngspice** is available at the *non-free* Debian repository. Before trying to install it, edit the file **/etc/apt/sources.list** as **root** and make sure the keyword *non-free* is present in the repository details. For example: ``deb http://ftp.us.debian.org/debian/ jessie main non-free``.
  
Create a temporary folder and change to it:

.. code-block:: none

  $ cd ~
  $ mkdir temp_caneda
  $ cd temp_caneda
      
.. note:: Current Debian stable release Jessie does not support the Qt 5 version of Qwt yet. It is supported in Stretch (currently testing), so its source package must be downloaded and compiled in order to install Caneda, as described below. 

Download the latest `Qwt libraries`_  (e.g. release 6.1.2) and unpack it:

.. _`Qwt libraries`: https://sourceforge.net/projects/qwt/files/latest/download

.. code-block:: none

  $ tar -xvf qwt-6.1.2.tar.bz2

Change to Qwt folder to configure and compile the source code:

.. code-block:: none

  $ cd qwt-6.1.2
  $ /usr/lib/x86_64-linux-gnu/qt5/bin/qmake qwt.pro
  $ make

Install Qwt into the system:

.. code-block:: none

  # make install
  
Go back to the temporary folder created earlier:

.. code-block:: none

  $ cd ~/temp_caneda

Get the latest Caneda *git* snapshot:

.. code-block:: none

  $ git clone https://github.com/caneda/caneda

.. note:: The default Caneda distribution is *master* (stable). Execute ``git checkout develop`` to compile the *develop* (latest) distribution.
    
Alternatively, download either `master`_ or `develop`_ tarball from the GitHub repository and unpack it:

.. _`master`:  https://github.com/Caneda/Caneda/tarball/master
.. _`develop`: https://github.com/Caneda/Caneda/tarball/develop
  
.. code-block:: none

  $ tar -xvf Caneda-Caneda-<version>.tar.gz
    
Create the folder ``build`` at the top of the source code structure and change into it:

.. code-block:: none

  $ cd caneda
  $ mkdir build
  $ cd build
    
Configure the source package and start the compilation process:

.. code-block:: none

  $ cmake ../
  $ make
    
Install Caneda into the system by executing:

.. code-block:: none

  # make install
      
To open Caneda, point explicitly to Qwt 6.1.2 library path as follows:
    
.. code-block:: none

  $ LD_LIBRARY_PATH=/usr/local/qwt-6.1.2/lib/ caneda &

.. note:: Usually Caneda is opened from Application Launcher or by executing ``caneda`` from command line, but Qwt is installed by default into a folder where the operating system cannot locate it. For these reason, the Application Launcher shortcut will not work in Debian stable.

The temporary folder ``~/temp_caneda`` may be deleted at this point.

