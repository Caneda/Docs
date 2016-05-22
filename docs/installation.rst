############
Installation
############

*********
GNU/Linux
*********

The installation procedure of Caneda in GNU/Linux may differ between distributions.
Execute ``lsb_release -da`` from a system console to check the Linux distribution name and release. Then select the installation instructions accordingly.

Debian 9 Stretch/Testing
========================

Caneda can be downloaded and installed right from the Debian repository by using the package manager **aptitude**. For more information, go to `Debian Packages`_.

.. _`Debian Packages`: https://packages.debian.org/testing/caneda

The following instructions to install Caneda are meant to be executed at the system console.
Consider the prefix ``$`` for non-privileged user commands and the prefix ``#`` for root commands.

Make sure the system package list is updated by executing:

.. code-block:: example

  # aptitude update

Install packages ``caneda`` (main) and ``ngspice`` (simulation engine) by simply executing:

.. code-block:: example

  # aptitude install caneda ngspice

.. note:: The simulation engine **Ngspice** is a *non-free* package. Before trying to install it, edit the file **/etc/apt/sources.list** as ``root`` and make sure the keyword ``non-free`` is present in the repository details. For example: ``deb http://ftp.us.debian.org/debian/ stretch main non-free``.

To open Caneda from KDE Application Launcher, go to **Applications** > **Development** and then click on *Caneda*. 

Alternatively, open Caneda from a terminal emulator (e.g. Konsole) by executing ``caneda &``.

Debian 8 Jessie/Stable
======================

Although Caneda is not currently available at the Debian repository for Jessie/Stable, it can be installed from its source code. 
Please read **Compilation for Debian 8 Jessie/Stable** for detailed instructions.

