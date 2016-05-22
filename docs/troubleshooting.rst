.. _troubleshooting:

###############
Troubleshooting
###############

To locate an issue, please enter a few keywords at **Search docs** or use the document tree on the left.

*********
Libraries
*********

**NO COMPONENTS ARE LISTED AFTER A REINSTALLATION WITH A FOLDER LOCATION CHANGE**

If Caneda was reinstalled to another folder location, when opened, it show few components available, or none at all.

This is due to the old paths configuration, which points to libraries that are no longer there.

To regenerate the default libraries database, go to *Settings* and delete one by one every library path. Then close Caneda and open it again. The issue should now be fixed.

***********
Compilation
***********

**BASH: CMAKE: COMMAND NOT FOUND**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none 

  bash: cmake: command not found

Check if package ``cmake`` is installed by executing ``aptitude show cmake``. If it is actually not installed, execute ``aptitude install cmake`` as root. Then try again.

It is recommended to install the following packages at once, to avoid further compilation errors:

.. code-block:: none 

  cmake
  g++
  qtbase5-dev 
  libqt5svg5-dev
  qttools5-dev
  qttools5-dev-tools

It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**CMAKE ERROR AT CMAKELISTS.TXT:3 (PROJECT): NO CMAKE_CXX_COMPILER COULD BE FOUND.**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none 

  -- The C compiler identification is GNU 4.9.2
  -- The CXX compiler identification is unknown
  -- Check for working C compiler: /usr/bin/cc
  -- Check for working C compiler: /usr/bin/cc -- works
  -- Detecting C compiler ABI info
  -- Detecting C compiler ABI info - done
  CMake Error at CMakeLists.txt:3 (PROJECT):
    No CMAKE_CXX_COMPILER could be found.

    Tell CMake where to find the compiler by setting either the environment
    variable "CXX" or the CMake cache entry CMAKE_CXX_COMPILER to the full path
    to the compiler, or to the compiler name if it is in the PATH.


  -- Configuring incomplete, errors occurred!
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeOutput.log".
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeError.log".

Check if C++ compiler is installed by executing ``aptitude show g++``. If it is actually now installed, execute ``aptitude install g++`` as root. Then try again.

It is recommended to install the following packages at once, to avoid further compilation errors:

.. code-block:: none 

  g++
  qtbase5-dev 
  libqt5svg5-dev
  qttools5-dev
  qttools5-dev-tools

It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**CMAKE ERROR AT CMAKELISTS.TXT:14 (FIND_PACKAGE): BY NOT PROVIDING "FINDQT5WIDGETS.CMAKE" IN CMAKE_MODULE_PATH...**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none 

  -- The CXX compiler identification is GNU 4.9.2
  -- Check for working CXX compiler: /usr/bin/c++
  -- Check for working CXX compiler: /usr/bin/c++ -- works
  -- Detecting CXX compiler ABI info
  -- Detecting CXX compiler ABI info - done
  CMake Error at CMakeLists.txt:14 (FIND_PACKAGE):
    By not providing "FindQt5Widgets.cmake" in CMAKE_MODULE_PATH this project
    has asked CMake to find a package configuration file provided by
    "Qt5Widgets", but CMake did not find one.

    Could not find a package configuration file provided by "Qt5Widgets"
    (requested version 5.3.2) with any of the following names:

      Qt5WidgetsConfig.cmake
      qt5widgets-config.cmake

    Add the installation prefix of "Qt5Widgets" to CMAKE_PREFIX_PATH or set
    "Qt5Widgets_DIR" to a directory containing one of the above files.  If
    "Qt5Widgets" provides a separate development package or SDK, be sure it has
    been installed.


  -- Configuring incomplete, errors occurred!
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeOutput.log".
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeError.log".

Install the Qt 5 base and SVG support definitions by executing ``aptitude install qtbase5-dev`` as root user, which in turn will install other required Qt 5 packages. Then, try again.

It is recommended to install the following packages at once, to avoid further compilation errors:

.. code-block:: none 

  qtbase5-dev 
  libqt5svg5-dev
  qttools5-dev
  qttools5-dev-tools
  
It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**MAKE ERROR AT CMAKELISTS.TXT:15 (FIND_PACKAGE): BY NOT PROVIDING "FINDQT5SVG.CMAKE" IN CMAKE_MODULE_PATH...**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none

  CMake Error at CMakeLists.txt:15 (FIND_PACKAGE):
    By not providing "FindQt5Svg.cmake" in CMAKE_MODULE_PATH this project has
    asked CMake to find a package configuration file provided by "Qt5Svg", but
    CMake did not find one.

    Could not find a package configuration file provided by "Qt5Svg" (requested
    version 5.3.2) with any of the following names:

      Qt5SvgConfig.cmake
      qt5svg-config.cmake

    Add the installation prefix of "Qt5Svg" to CMAKE_PREFIX_PATH or set
    "Qt5Svg_DIR" to a directory containing one of the above files.  If "Qt5Svg"
    provides a separate development package or SDK, be sure it has been
    installed.


  -- Configuring incomplete, errors occurred!
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeOutput.log".
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeError.log".

Install the Qt 5 SVG support definitions by executing ``aptitude install libqt5svg5-dev`` as root user. Then, try again.

It is recommended to install the following packages at once, to avoid further compilation errors:

.. code-block:: none

  libqt5svg5-dev
  qttools5-dev
  qttools5-dev-tools

It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**MAKE ERROR AT CMAKELISTS.TXT:17 (FIND_PACKAGE): BY NOT PROVIDING "FINDQT5LINGUISTTOOLS.CMAKE" IN CMAKE_MODULE_PATH...**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none

  CMake Error at CMakeLists.txt:17 (FIND_PACKAGE):
    By not providing "FindQt5LinguistTools.cmake" in CMAKE_MODULE_PATH this
    project has asked CMake to find a package configuration file provided by
    "Qt5LinguistTools", but CMake did not find one.

    Could not find a package configuration file provided by "Qt5LinguistTools"
    (requested version 5.3.2) with any of the following names:

      Qt5LinguistToolsConfig.cmake
      qt5linguisttools-config.cmake

    Add the installation prefix of "Qt5LinguistTools" to CMAKE_PREFIX_PATH or
    set "Qt5LinguistTools_DIR" to a directory containing one of the above
    files.  If "Qt5LinguistTools" provides a separate development package or
    SDK, be sure it has been installed.


  -- Configuring incomplete, errors occurred!
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeOutput.log".
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeError.log".

Install the Qt 5 SVG support definitions by executing ``aptitude install qttools5-dev`` as root user, which in turn will install other required Qt 5 package. Then, try again.

It is recommended to install the following packages at once, to avoid further compilation errors:

.. code-block:: none

  qttools5-dev
  qttools5-dev-tools
  
It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**CMAKE ERROR AT /USR/LIB/X86_64-LINUX-GNU/CMAKE/QT5LINGUISTTOOLS/QT5LINGUISTTOOLSCONFIG.CMAKE:22 (MESSAGE)...**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none

  CMake Error at /usr/lib/x86_64-linux-gnu/cmake/Qt5LinguistTools/Qt5LinguistToolsConfig.cmake:22 (message):
    The package "Qt5LinguistTools" references the file

      "/usr/lib/x86_64-linux-gnu/qt5/bin/lrelease"

    but this file does not exist.  Possible reasons include:

    * The file was deleted, renamed, or moved to another location.

    * An install or uninstall procedure did not complete successfully.

    * The installation package was faulty and contained

      "/usr/lib/x86_64-linux-gnu/cmake/Qt5LinguistTools/Qt5LinguistToolsConfig.cmake"

    but not all the files it references.

  Call Stack (most recent call first):
    /usr/lib/x86_64-linux-gnu/cmake/Qt5LinguistTools/Qt5LinguistToolsConfig.cmake:38 (_qt5_LinguistTools_check_file_exists)
    CMakeLists.txt:17 (FIND_PACKAGE)


  -- Configuring incomplete, errors occurred!
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeOutput.log".
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeError.log".

Install the Qt 5 SVG support definitions by executing ``aptitude install qttools5-dev-tools`` as root user. Then, try again.
  
It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**CMAKE ERROR AT /USR/SHARE/CMAKE-3.0/MODULES/FINDPACKAGEHANDLESTANDARDARGS.CMAKE:136 (MESSAGE)...**

After executing ``cmake ../`` to install Caneda, the following error occurs:

.. code-block:: none

  CMake Error at /usr/share/cmake-3.0/Modules/FindPackageHandleStandardArgs.cmake:136 (message):
    Could NOT find Qwt (missing: QWT_LIBRARY QWT_INCLUDE_DIR) (Required is at
    least version "6.1.2")
  Call Stack (most recent call first):
    /usr/share/cmake-3.0/Modules/FindPackageHandleStandardArgs.cmake:343 (_FPHSA_FAILURE_MESSAGE)
    cmake/Modules/FindQwt.cmake:94 (FIND_PACKAGE_HANDLE_STANDARD_ARGS)
    CMakeLists.txt:22 (FIND_PACKAGE)


  -- Configuring incomplete, errors occurred!
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeOutput.log".
  See also "/home/user/caneda/caneda/build/CMakeFiles/CMakeError.log".

Download qwt 6.1.2 and extract the tar.gz file into a temporary folder.

Compile qwt with Qt5:

.. code-block:: none

  $ /usr/lib/x86_64-linux-gnu/qt5/bin/qmake qwt.pro
  $ make

If compilation finished without errors, install Qwt by executing ``make install`` with root privileges, in order to install qwt libraries into system folders.

Then, try again.

It is also recommended to install the optional package ``ngspice`` (simulation engine) as follows: ``aptitude install ngspice``.

To install a package from the *non-free* Debian repository, first edit **/etc/apt/sources.list**, add the keyword **non-free** at the end of the distribution description (e.g. ``deb http://ftp.us.debian.org/debian/ stable main non-free``) and then execute ``aptitude update`` as root. Finally, execute ``aptitude install <package>``.

**CANEDA: ERROR WHILE LOADING SHARED LIBRARIES: LIBQWT.SO.6: CANNOT OPEN SHARED OBJECT FILE: NO SUCH FILE OR DIRECTORY**

After executing ``caneda`` from a terminal emulator, the following error is displayed:

.. code-block:: none

  caneda: error while loading shared libraries: libqwt.so.6: cannot open shared object file: No such file or directory
  
If qwt 6.1.2 was installed from its source, the operating system does not know how to reach these libraries.

The solution is to execute Caneda from command line as follows:

.. code-block:: none

  $ LD_LIBRARY_PATH=/usr/local/qwt-6.1.2/lib/ caneda

Then, Caneda GUI should be displayed.

  