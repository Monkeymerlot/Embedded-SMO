# Embedded-SMO
Remake of JKI's Embedded SMO, using by Value principles. This class has been expanded to be a part of the MAUI Framework (see below). Note: this software is in no way, shape or form endorsed nor reviewed by James Kring, inc. (JKI). Futhermore, this project is currently in alpha, and should be considered unstable.

# MAUI Framework
Note: The MAUI Framework is currently in beta and should be considered unstable.
## About
MAUI is dynamically linked, rapid development UI platform based on subpanels and implemented using [JKI's SMOs](https://github.com/JKISoftware/JKI-State-Machine-Objects). 

Subpanels are oftentimes passed up for other UI elements such as tab controls due to their complexity involving reference management, insertion of VIs, ensuring that the VIs are running etc. However, they provide a very good way to show different views in a clean and organized fashion. Furthermore, they are extremely modular, allowing for subpanels in subpanels, as well as providing a consistent look across many different views that can be totally independent and decoupled from one another. Careful consideration of the pros and cons of subpanels led me to realize that much of the complexity can be abstracted away, providing a simplified interface for an owning application. 

In addition to subpanels, another theme that I recognized across good software is dynamic linking of dependencies. Instead of having everything together in a single project or statically linked on the block diagram, subpanels, since they are independent VIs, can be loaded from disk at runtime. This has serious benefits for project management and working on projects in a team with a compiled, non-textual language (ie LabVIEW). 

These two ideas combined provide the basis for the MAUI Framework. MAUI works by having a Main UI (MAUI-Template) that contains subpanels. During startup, the MAUI framework will automatically locate subpanels (Embedded-Template) either through configuration based dependency injection or by searching a default subdirectory. This means that subpanels can be developed totally independent of one another and different systems can use the same main program and implement different features by implementing different subpanels. 

It should be noted that the Embedded Engine is just one part of a larger framework that consists of the MAUI Engine, MAUI Template, Embedded Engine, and the Embedded Template.

## What is the Embedded *Engine*?
The embedded engine is a class that is based on the JKI SMO framework and abstracts away the complexities of embedding a VI into a subpanel. This was initially a remake of the JKI SMO Embedded_UI, however the installation of this class seemed to break the SMO framework for some reason. Furthermore, I prefer to use by-Value SMOs since they seem to follow the dataflow principles of LabVIEW a little better than a by-Reference SMO. This differs from JKI's Embedded_UI, which is based off of by-reference principles. This class performs all of the critical functions for the Embedded SMO template, which inherits from this class. The idea is to abstract away as much as possible from the end user. I also went on to add more features to this class to allow it to be a part of the MAUI Framework.

## Getting Started Using the MAUI Framework
In order to get started with the MAUI framework, only a working knowledge of the JKI SMO framework is needed. The easiest way is to use the JKI SMO editor to create a SMO.UI.MAUI.Basic from the MAUI Template. Once the template is created, you should have a folder of the same name as the template. The fastest way to get started is to create a subdirectory in this folder named `Subpanels`. Once the subdirectory is created and named, make at least two subpanels from the SMO.UI.Embed.Basic template, having them saved to the aforementioned subdirectory you created. After saving all of the files in the project, you can go ahead and run the "TestLauncher.vi" of the MAUI class object. You should see two VIs embedded in the subpanels, and the corresponding ring controls displaying the class names of those subpanels.

## Dependencies
JKI State Machine Objects Framework

## How to Install
To be finished

## Credits
The MAUI Framework, including the Embedded Engine, is maintained by Levylab, a research group at the University of Pittsburgh's Department of Physics and Astronomy. Furthermore, this work is derivative of prior work produced by JKI Software. However, they do not endorse this product in any way, shape or form.

## License
The MAUI Framework is distributed under the open source three clause BSD license providing everyone right to use and distribute both souce code and compiled versions of the MAUI Framework. See LICENSE file for details.

## Github Repository
https://github.com/levylabpitt/Embedded-SMO
