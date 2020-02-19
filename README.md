# armor_owloop
The classic ARMOR (**A** **R**OS **M**ulti-**O**ntology **R**eference) can be found [here](https://github.com/EmaroLab/armor).
This repository instead is an extention of [ARMOR](https://arxiv.org/abs/1706.10151) based on OWLOOP to implement the [SIT](https://ieeexplore.ieee.org/abstract/document/8956457) algorithm, which is injected in the ARMOR service.

# Installation
- `cd ros_ws/src/`
- `git clone https://github.com/EmaroLab/injected_armor_pkgs.git`
- `cd injected_armor_pkgs/`
- `git submodule update --init --recursive --remote`
- optionally update to the last version 
      - `git submodule foreach git pull origin master`
      - `git submodule foreach git checkout master`
- `cd ../..`
- `catkin_make`

# Overview 

This repository contains [ROSJAVA](http://wiki.ros.org/rosjava) packages for managing OWL ontologies in a robotic architecture.
In particular the repository contains four sub-repositories:
- [ARMOR](https://github.com/EmaroLab/ros_multi_ontology_references) is a ROS service that allows to manipulate and query ontologies.
- [OWLOOP](https://github.com/EmaroLab/owloop) is Java API that can be used for advanced manipulation and queries. OWLOOP would be injected in ARMOR to augment its capability with custom interfaces. This package is considered as a library.
- [SIT](https://github.com/EmaroLab/scene_identification_tagging) is a symbolic-base algorithm for learning and structuring scenes as classes in an ontology based on OWLOOP. This package is considered as a library.
- [SIT-service](https://github.com/EmaroLab/sit_armor) SIT uses OWLOOP to allow ARMOR provinding interface for learning and recognising scenes. Those interfaces are defined inside the SIT-service component.

For more information  please check the `README` file and the documentations inside each sub-repository of the above lists (Note that the most updated documentation is always **in the master branch**).

## Contacts

For comment, discussions or support refer to this git repository open issues before to contact us (more detailed contacts to the authors is further specified in each module)
 - [luca.buoncompagni@edu.unige.it](mailto:luca.buoncompagni@edu.unige.it).


