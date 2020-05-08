# Embedded-SMO
Remake of JKI's Embedded SMO, using by Value principles. Note: this software is in no way, shape or form endorsed nor reviewed by James Kring, inc. (JKI). Futhermore, this project is currently in beta, and should be considered unstable.

##What is the Embedded Engine?
The embedded engine is a class that is based on the JKI SMO framework and abstracts away the complexities of embedding a VI into a subpanel. This was initially a remake of the JKI SMO Embedded_UI, however the installation of this class seemed to break the SMO framework upon installation. Furthermore, I prefer to use by-Value SMOs, which differ from JKI's Embedded_UI, which is based off of by-reference principles. This class performs all of the critical functions for the Embedded SMO template, which inherits from this class. The idea is to abstract away as much as possible from the end user.
