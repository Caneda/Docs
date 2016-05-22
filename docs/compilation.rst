###########
Compilation
###########

Caneda source code is hosted by GitHub. For more information, see `Caneda on GitHub`_.

.. _`Caneda on GitHub`: https://github.com/Caneda/Caneda

*********
GNU/Linux
*********

The compilation procedure of Caneda in GNU/Linux may differ between distributions. Execute ``lsb_release -da`` from a system console to check the Linux distribution name and release. Then select the compilation instructions accordingly.

Debian 9 Stretch/Testing
========================

The following instructions to compile Caneda are meant to be executed at the system console.
Consider the prefix ``$`` for non-privileged user commands and the prefix ``#`` for root commands.

Use **aptitude** to install the required/suggested packages:

.. code-block:: example

  # aptitude install git cmake g++ qtbase5-dev libqt5svg5-dev qttools5-dev qttools5-dev-tools ngspice libqwt-qt5-dev 
    
.. note:: The simulation engine **Ngspice** is a *non-free* package. Before trying to install it, edit the file **/etc/apt/sources.list** as ``root`` and make sure the keyword ``non-free`` is present in the repository details. For example: ``deb http://ftp.us.debian.org/debian/ stretch main non-free``.
      
Go to home folder and download Caneda source code using *git*:

.. code-block:: example

  $ cd ~
  $ git clone https://github.com/caneda/caneda

.. note:: The default Caneda distribution is *master* (stable). To compile and install the *develop* distribution (latest), optionally execute ``git checkout develop`` after the download is completed.
    
Optionally, download the `master`_ or the `develop`_ tarball and unpack it: 

.. _`master`: https://github.com/Caneda/Caneda/tarball/master
.. _`develop`: https://github.com/Caneda/Caneda/tarball/develop
  
.. code-block:: example

  $ cd ~
  $ tar -xvf Caneda-Caneda-<version>.tar.gz
    
Create the folder ``build`` at the top of the source code structure and change into it:

.. code-block:: example

  $ cd caneda
  $ mkdir build
  $ cd build
    
Configure the source package and start the compilation process:

.. code-block:: example

  $ cmake ../
  $ make
    
Install Caneda into the system folders by executing:

.. code-block:: example

  # make install
      
To open Caneda from KDE Application Launcher, open **Applications** > **Development** and then click on *Caneda*. 

Alternatively, open Caneda from a terminal emulator (e.g. Konsole) by executing ``caneda &``.

Debian 8 Jessie/Stable
======================

The following instructions to compile Caneda are meant to be executed at the system console.
Consider the prefix ``$`` for non-privileged user commands and the prefix ``#`` for root commands.

Use **aptitude** to install the required/suggested packages:

.. code-block:: example

  # aptitude install git cmake g++ qtbase5-dev libqt5svg5-dev qttools5-dev qttools5-dev-tools ngspice``

.. note:: The simulation engine **Ngspice** is a *non-free* package. Before trying to install it, edit the file **/etc/apt/sources.list** as ``root`` and make sure the keyword ``non-free`` is present in the repository details. For example: ``deb http://ftp.us.debian.org/debian/ stretch main non-free``.
  
Download latest `Qwt libraries`_  to home folder and unpack it:

.. _`Qwt libraries`: https://sourceforge.net/projects/qwt/files/latest/download

.. code-block:: example

  $ cd ~
  $ tar -xvf qwt-<version>.tar.bz2

.. note:: Debian current stable distribution (Jessie) does not support Qwt yet (it is to be supported in Stretch, currently testing distribution), so its source package must be downloaded and compiled in order to install Caneda, as described below. 

Change to Qwt folder to configure and compile the source code:

.. code-block:: example

  $ cd qwt-<version>
  $ /usr/lib/x86_64-linux-gnu/qt5/bin/qmake qwt.pro
  $ make

Install Qwt into system folders:

.. code-block:: example

  # make install
  
Go to home folder and download Caneda source code using *git*:

.. code-block:: example

  $ cd ~
  $ git clone https://github.com/caneda/caneda

.. note:: The default Caneda distribution is *master* (stable). To compile and install the *develop* distribution (latest), optionally execute ``git checkout develop`` after the download is completed.
    
Optionally, download the `master`_ or the `develop`_ tarball and unpack it: 

.. _`master`: https://github.com/Caneda/Caneda/tarball/master
.. _`develop`: https://github.com/Caneda/Caneda/tarball/develop
  
.. code-block:: example

  $ cd ~
  $ tar -xvf Caneda-Caneda-<version>.tar.gz
    
Create the folder ``build`` at the top of the source code structure and change into it:

.. code-block:: example

  $ cd caneda
  $ mkdir build
  $ cd build
    
Configure the source package and start the compilation process:

.. code-block:: example

  $ cmake ../
  $ make
    
Install Caneda into the system folders by executing:

.. code-block:: example

  # make install
      
To open Caneda, point explicitly to Qwt library path as follows:
    
.. code-block:: example

  $ LD_LIBRARY_PATH=/usr/local/qwt-6.1.2/lib/ caneda &

.. note:: Usually Caneda is opened from KDE Application Launcher or by executing ``caneda`` from command line, but Qwt is installed by default into a folder where the operating system cannot locate it. 


