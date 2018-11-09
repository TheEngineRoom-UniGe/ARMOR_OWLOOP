# injected_armor
an extention of [ARMOR](https://arxiv.org/abs/1706.10151) with OWLOOP and the injected service SIT.

# Overview 

This repository contains a [ROSJAVA](http://wiki.ros.org/rosjava) packages for managing OWL ontologies in a robotic architecture.
The repository contains three ROS packages:
- [injected_armor_msgs](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/injected_armor_msgs): contains the definition of the messages for interacting with the ontology through ARMOR ROS service.
- [injected_armor](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/injected_armor): contains the services and libraries for interacting with OWL ontologies.
- [armor_py_client_api](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/armor_py_client_api): contains an example, a test script, and common utility fot using ARMOR from a Python ROS client. 

The `injected_armor` package contains three modules:
- [amor](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/injected_armor/amor): is the Java library that interacts with OWL API and Reasoners in a trade safe manner. This is the core for using OWL ontologies.
- [owloop](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/injected_armor/owloop): is an extension of `amor` that allows to interact with ontology in an Object Oriented Programming manner.
- [armor](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/injected_armor/armor): is a ROS service that depends on `amor` and `injected_armor_msgs` for allow ROS clients to manipulate ontologies from other packages.
- [sit](https://github.com/EmaroLab/injected_armor_pkgs/tree/master/injected_armor/sit): is a library that implements the Scene Identification and Tagging (SIT) algorithm. It depends on `owloop` (which consequentially depends on `amor`). This library should be used by `armor` in order to inject a new service. 

Please check the `README` file and `Doc` folder inside each components of the above lists for more information. 
All of them have been imported from their original repository, which is linked inside the documentation of each module.

# Instalation

This repository must be a child of the src folder in your workspace to reach the maven repository (set in the `build.gradle` inside each module as `../../../../devel/share/maven/`).

Run `catkin_make` and test the basic armor service with
``roslaunch armor_py_client_api armorTest.launch``

# Todo

A sit test is starting (at line 46 in [this file](https://github.com/EmaroLab/injected_armor_pkgs/blob/master/injected_armor/armor/src/main/java/it/emarolab/armor/ARMORMainService.java)) by default as an *hello world* example, where you should set the correct path of the ontology (at line 33 in [this file](https://github.com/EmaroLab/injected_armor_pkgs/blob/master/injected_armor/sit/src/main/java/it/emarolab/sit/SITBase.java)).

Those lines (toughener with the message definitions in `injected_armor_msgs`), whould be change in order to allow a ROS client to call the SIT algorithm through an `armor` request.


## Contacts

For comment, discussions or support refer to this git repository open issues before to contact us (more detailed contacts to the author is further specified in each module)
 - [luca.buoncompagni@edu.unige.it](mailto:luca.buoncompagni@edu.unige.it).


