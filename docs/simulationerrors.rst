Simulation Errors
=================
There are several errors that can occur during a simulation. Following there are hints to help you solve the most common errors.

Missing simulator backend
-------------------------
To simulate a schematic circuit, Caneda can use several simulation backends. Currently, the recommended backend is the *ngspice* simulator. Although you can use other alternatives, *ngspice* is the default value. If the simulator is not installed on your system, this error may arise. To solve this error, you must install *ngspice* on your system. You may install *ngspice* either from your normal distribution channels or repositories, or manually downloading the required files from the official *ngspice* webpage. The following resources will help you to install *ngspice*:

* http://ngspice.sourceforge.net/download.html
* http://ngspice.sourceforge.net/packages.html
* https://packages.debian.org/search?keywords=ngspice
* https://launchpad.net/ubuntu/+source/ngspice
* https://www.archlinux.org/packages/community/x86_64/ngspice/

Missing ground net
------------------

Missing simulation profile
--------------------------
