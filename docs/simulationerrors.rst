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

.. image:: /images/ngspice.png

Missing ground net
------------------
While performing simulations, it is always important to include at least one ground net. You can also include several ground nets and they will be all linked together. Ground nets allow the simulation to calculate the values of each node and complete successfully. They will also serve as reference nodes to the rest of the circuit, so when you inspect the resulting simulation waveforms you will know that the voltage values are calculated with respect to the ground nets.

To add a ground net, simply select the *ground* component from the *components sidebar* and insert it in any net you like.

.. image:: /images/ground.png

Missing simulation profile
--------------------------
Simulation profiles are the actual commands indicating the simulation backends what kind of simulation to perform. There are several kinds of simulation profiles and which one you will choose depends on your actual needs. Some examples include transient simulations, AC simulations, operating point calculations, DC transfer function analysis, etc.

To add a simulation profile, simply select a *simulation* component from the *components sidebar* and insert it anywhere in the schematic.

.. image:: /images/simulationProfiles.png
