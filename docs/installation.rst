############
Installation
############

*********
GNU/Linux
*********

.. note:: To obtain the distribution name and release of a particular system, execute ``lsb_release -da`` from a system console.

Debian 9 Stretch/Testing
========================

Caneda can be downloaded and installed right from the Debian repository by using the package manager **aptitude**. For more information, go to `Debian Packages`_.

.. _`Debian Packages`: https://packages.debian.org/testing/caneda

The following instructions to install Caneda are meant to be executed at the system console.
Consider the prefix ``$`` for non-privileged user commands and the prefix ``#`` for root commands.

Make sure the system package list is updated by executing:

.. code-block:: none

  # aptitude update

Install **Caneda** (main) and **Ngspice** (simulation engine) by simply executing:

.. code-block:: none

  # aptitude install caneda ngspice

.. note:: The simulation engine **Ngspice** is available at the *non-free* Debian repository. Before trying to install it, edit the file **/etc/apt/sources.list** as **root** and make sure the keyword *non-free* is present in the repository details. For example: ``deb http://ftp.us.debian.org/debian/ stretch main non-free``.

To open Caneda from the Application Launcher, go to **Applications** > **Development** and then click on *Caneda*. 

Alternatively, open Caneda from a terminal emulator by executing ``caneda &``.

Debian 8 Jessie/Stable
======================

Although Caneda is not currently available at the Debian repository for Jessie/Stable, it can be installed from its source code. 
Please read :doc:`compilation` for step-by-step instructions.

*****************
Microsoft Windows
*****************

Caneda *stable* release is currently supported in Microsoft Windows systems. 

Simply download the Caneda installation executable `CanedaInstaller_<latest>.exe`_ and double-click it to begin the installation process. 

.. _`CanedaInstaller_<latest>.exe`: https://github.com/Caneda/Caneda/releases/download/0.2.0/CanedaInstaller_0.2.0.exe
