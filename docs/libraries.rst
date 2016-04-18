Component libraries
===================
There is a certain point in any design where the user needs to find extra components to those found in any EDA application. Caneda has several methods to add new components, which are described below.


Spice models
------------
In Caneda you can modify a component's model or use an external spice model for your simulations. For every component there are basically three methods to modify a component's model:

  * Modify the basic parameters of the model.
  * Use a *model component* and modify the needed parameters.
  * Include an external library file and use a model from the library.

Modify the basic parameters of the model
########################################
The easier way to modify a component's behaviour is to modify the basic parameters of the model. In order to do so, include a component and edit its parameters with the required values.

.. image:: /images/parametersDialog.png

Use a model component
#####################
If you need to modify more parameters than those available in the basic parameters, you can include a *model component*. There are several *model components* for different kind of devices including (but not limited to) transistors, diodes, transmission lines, switches, capacitors and inductors. You can also use this method if you have several components of the same type and you don't want to type the same parameter's values for each component. After you include the *model component*, edit its parameters and use its ``name`` as the ``model`` field (parameter) in every instance of the component.

.. image:: /images/modelComponent.png

Include an external library file
################################
A similar alternative to using a *model component* is to include an external library file (a text file containing the model name and all the parameters' values) and use the model's ``name`` as the ``model`` field (parameter) in all the components needed. To include the external library file you can use the *library* or the *include* component. The main difference between an *include* and a *library* is that while in an *include* you can have only one reference for each model (defining its parameters), in a *library* you can have multiple references for each model (one in each library of the library file). In this way, for example, you could have a library with the typical, a library with the maximum and a library with the minimum parameters of a component (all in one file) and include the library you need in the simulation you are performing.

.. image:: /images/includeDirective.png

The advantage of using an external library file over the previous methods is that you can download the needed model or library from the web and use it directly in your design without needing to manually copy every parameter to a *model component*. This method is similar to that found in commercial simulation programs.

When using library files it is important to note that when using complex components described by spice subcircuits both the number of ports and the number of parameters must be equal between the symbol used and the model included in the library file. If using for example an opamp, and the number of pins between the spice library file and the symbol is not the same, a new opamp symbol must be created with the same number of pins as the component in the spice library file. This also holds true for the number of parameters (usually zero for a downloaded commercial model).

In the repository folder hosted at `Spice Models <https://github.com/Caneda/Examples/tree/master/spice_models>`_ you will find some basic examples using the previously described methods. The included models in the provided examples are not based on real data, but rather manually modified for educational purposes only.


Custom libraries
----------------
This example shows how to create a custom library with user created components.

In Caneda, libraries are simply folders with schematics and symbols inside. For each component created, both a schematic describing the electric circuit and a symbol with the component representation must exist. The connection between the schematic and the symbol is performed by the use of ports in both files. Each port in the schematic will be connected with the corresponding port in the symbol, matching both ports by name. Parameters may be exposed in the symbol and each parameter will be matched to a parameter in the schematic. In this case, the parameter name only in the schematic must be enclosed by brackets ``{}`` indicating a spice parameter operation. Mathematical operations are supported, giving extra flexibility.

For example, if a custom resistor was to be created, the symbol would contain the drawing, two ports and a parameter named ``{R_custom}``. On the other hand, the schematic would contain the same two ports and a resistor (describing the simple electric circuit of a resistor) with a value ``R={R_custom}``. In the same way, the value could be ``R={R_custom*2/2}`` using mathematical operations together with the parameter.

Finally, to add the recently created library to Caneda, open the *Application Settings* dialog and in the *Libraries* section add the custom created library by selecting its folder. Any successive change in the library will be reflected upon the next program restart. 

.. image:: /images/librariesSettings.png

In the repository folder hosted at `Custom Library <https://github.com/Caneda/Examples/tree/master/custom_library>`_, you will find a couple of components created to show the previously described procedure. The example components are ready to use, and if you download the whole folder you can include it in your project by adding the folder as a library to Caneda.


Extra libraries repository
--------------------------
Finally Caneda has a special repository which holds extra libraries and components, ready to use. If you download a whole folder from that repository you can include it in your project by adding the folder as a library to Caneda.

Caneda's libraries repository is hosted at:

https://github.com/Caneda/Libraries

To use any library, you must download the selected folder and add it to your library list through the *Application Settings* dialog in the *Libraries* section. Any successive change in the library will be reflected upon the next program restart.
