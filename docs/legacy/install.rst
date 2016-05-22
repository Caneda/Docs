Installation Instructions
=========================
The following are generic instructions to compile and install Caneda on your system.

Requirements
------------
In order to compile Caneda sources, you will need the following libraries installed in your system:

  * Qt
  * Cmake
  * Qwtplot


Getting the Latest Git Snapshot
-------------------------------
You can always get the latest Caneda version from our git repository. Please use an official release if you want to work with Caneda.  The git version might not even compile.

``$ git clone https://github.com/Caneda/Caneda``


Installation
------------
These are generic installation instructions.

If you need to do unusual things to compile the package, please try to figure out how *cmake* could check whether to do them, and mail diffs or instructions to the authors so they can be considered for the next release.

Unpack the distribution tarball:

``$ tar xvzf caneda-<version>.tar.gz``

Change into the source directory:

``$ cd caneda-<version>``

Create a new directory for cmake to work in:

``$ mkdir build``

Change into the recently created directory:

``$ cd build``

Configure the source package for your system:

``$ cmake ../``

Compile the package:

``$ make``

Install Caneda:

``$ make install``

You must have root privileges if you want to install the package in the standard location (``/usr/local``) or in any location that is only writable by root.


Compilers and Options
---------------------
Some systems require unusual options for compilation or linking that *cmake* does not know about.  Run ``./cmake --help`` for details on some of the pertinent environment variables.

You can give *cmake* initial values for configuration parameters by setting variables in the command line or in the environment.  Here is an example:

``$ ./cmake CC=c89 CFLAGS=-O2 LIBS=-lposix``


Installation Directory
----------------------
By default, ``make install`` will install the package's files in ``/usr/local/bin``, ``/usr/local/man``, etc.  You can specify an installation prefix other than ``/usr/local`` by giving *cmake* the option ``--prefix=PATH``.

You can specify separate installation prefixes for architecture-specific files and architecture-independent files.  If you give *cmake* the option ``--exec-prefix=PATH``, the package will use *PATH* as the prefix for installing programs and libraries. Documentation and other data files will still use the regular prefix.

In addition, if you use an unusual directory layout you can give options like ``--bindir=PATH`` to specify different values for particular kinds of files.


MIME Types and Files Association
--------------------------------
Optionally you may want to get Caneda's file types associated with the application itself. In order to do so, run the following command as root:

``$ update-mime-database /usr/local/share/mime``


Doxygen Documentation
---------------------
Caneda uses Doxygen as its developers code documentation. To generate the doxygen documentation, use the Doxyfile file provided at the source's root.
