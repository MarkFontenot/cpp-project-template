# Contents #

  1. Downloading the template.
  1. Template organization.
  1. Building the template.
  1. Editing the template.
  1. Customizing the template.
  1. Implementing the commandline main.
  1. Implementing the interactive main.
  1. Implementing the GUI main.
  1. Preferences.
  1. Logging.

# Downloading the Template #
You can download the [C/C++ Project Template](http://code.google.com/p/cpp-project-template/) from the [C++ Project Template](http://code.google.com/p/cpp-project-template/) main page. The [main page](http://code.google.com/p/cpp-project-template/) will always feature the latest version of the [C++ Project Template](http://code.google.com/p/cpp-project-template/). Older versions may be downloaded from the "Downloads" tab, but it is highly recommend that you download only the latest, featured version.

# Template Organization #
The template is organized as follows:

  * AUTHORS
  * CMakeLists.txt
  * COPYING
  * ChangeLog
  * Doxyfile
  * INSTALL
  * LICENSE
  * Makefile
  * README
  * bin/
  * build/
  * configure
  * docs/
  * include/
  * lib/
  * share/
  * src/
  * test/
  * thirdparty/
  * tools/

## AUTHORS ##
This is where contributors to the project should sign their names.

## CMakeLists.txt ##
This is the top-level build configuration file. It is used by [CMake](http://www.cmake.org/) for building the project. Please see the [CMake Manual](http://www.cmake.org/cmake/help/cmake2.6docs.html) for the full list of available commands.

## COPYING ##
You should place a plaintext copy of your project's license in this file. Or, you can put an English explanation of the rules of copying your source code, and refer the reader to the "LICENSE" file for the official license agreement that they must follow.

## ChangeLog ##
For each version, you should annotate the changes between versions in this file.

## Doxyfile ##
This file configures [Doxygen](http://www.stack.nl/~dimitri/doxygen/). Please see the [Doxygen Configuration Manual](http://www.stack.nl/~dimitri/doxygen/config.html) on how to customize this file to fit your needs.

## INSTALL ##
This is where you should place instructions for how to install your product. If you use CMake's builtin "INSTALL(...)" commands for indicating which files to install and where those files should go, then the content of this file should be something along the lines of "Build the project using 'make', then install using 'sudo make install'".

## LICENSE ##
You should place a plaintext copy of your project's license in this file.

## Makefile ##
This is a simple Makefile wrapper for "CMakeLists.txt". It allows you to build the CMake project with the usual invocation of "make", without ever having to invoke cmake.

## README ##
This is where you should place basic documentation for your project. It should include instructions on building your project, instructions on how to use or invoke your project, a list of known bugs, and any other information that you would like users to know.

## bin/ ##
This is where all executable files built by the project are generated. You can use the "ADD\_EXECUTABLE" command in CMake to specify additional executables to generate.

If you place this project in Subversion, you will probably want to set the "svn:ignore" property to "`*`" for this folder (i.e. "svn propset svn:ignore '`*`' bin").

## build/ ##
This is where CMake will generate intermediate build products, including CMake's variable and configuration cache. You should generally not touch this folder.

If you place this project in Subversion, you will probably want to set the "svn:ignore" property to "`*`" for this folder (i.e. "svn propset svn:ignore '`*`' build").

## configure ##
This BASH script invokes CMake. It is there so that user's who are familiar with the "./configure", then "make", then "sudo make install" will feel comfortable using your project. You do not need to touch or edit this file. You can use "make" directly, without first invoking "./configure", since the configuration step will run if necessary.

## docs/ ##
This is where the project's Doxygen documentation will be generated, if you invoke the "make docs" or "make doxygen" targets. If you place this project in a Subversion repository, you will probably want to invoke "svn propset svn:ignore '`*`' docs".

## include/ ##
You should place your project's public header files (i.e. the header files that you want the user's of your project to able to include) in a subfolder of "include/". The name of the subfolder should correspond to your project's name. The "include/" folder is automatically added to the header search paths, so if you create a master header file for your project named "projectname.h" and place it in "include/projectname/", then you will be able to include it from your source code using "#include <projectname/projectname.h>".

## lib/ ##
This is where all library files built by the project are generated. You can use the "ADD\_LIBRARY" command in CMake to specify additional libraries to generate.

If you place this project in Subversion, you will probably want to set the "svn:ignore" property to "`*`" for this folder (i.e. "svn propset svn:ignore '`*`' lib").

## share/ ##
You should place any data files that your project needs in a subfolder of this folder. The name of the subfolder should, in some way, correspond to your project's name.

## src/ ##
You should place your source files in this folder or in a subfolder of this folder. The "CMakeLists.txt" file in this directory will automatically compile all sources in the folder into a single executable. You may need to edit this "CMakeLists.txt" file, so that the appropriate build targets are generated (e.g. if you have multiple different executable or library modules, so  all sources should not be built into a single target).

## test/ ##
You should place your test sources in this folder. The [UnitTest++](http://unittest-cpp.sourceforge.net/) unit-testing framework is currently being used by default. Using this particular framework is highly recommended.

## thirdparty/ ##
If you would like to bundle thirdparty dependencies with your project, this would be a reasonable location to place them. Otherwise, you can delete this folder.

## tools/ ##
This contains any scripts, CMake modules, or other components that are needed to build the project or which facilitate project building and development. If you create a script to stylize the code according to your project's specifications or if you create a script to validate that project guidelines are being followed, the "bin" subfolder of "tools" would be the appropriate location to place those scripts. If you need to add modules to CMake (e.g. to implement "FIND\_PACKAGE" for an additional package), you should place those scripts in "tools/share/cmake". You can already find examples of such modules for locating Log4Cxx and UnitTest++.

# Building the Template #
The project template requires:

  * A working C++ compiler.
  * The Make build system.
  * The CMake build system.
  * The pkg-config tool.
  * The Boost C++ libraries.
  * The Qt Framework.
  * The Log4Cxx library.
  * The UnitTest++ unit-testing framework.
  * A valid configuration for the PATH environment variable.
  * A valid configuration for the PKG\_CONFIG\_PATH environment variable.

For step-by-step instructions on setting up a C/C++ development environment see:
  * [C/C++ Development Environment Setup for Windows](http://sites.google.com/site/michaelsafyan/coding/resources/how-to-guides/development-environment-setup/cpp/windows)
  * [C/C++ Development Environment Setup for Mac OS X](http://sites.google.com/site/michaelsafyan/coding/resources/how-to-guides/development-environment-setup/cpp/mac-os-x)
  * [C/C++ Development Environment Setup for Ubuntu Linux](http://sites.google.com/site/michaelsafyan/coding/resources/how-to-guides/development-environment-setup/cpp/ubuntu)

Assuming you have all the prerequisites satisfied, building the project simply involves invoking "make". The typical "make clean" and "make distclean" targets also exist. You can type "make help" for a full list of build targets.

# Editing the Template #
You can edit the project template with the IDE or code editor of your choosing. I personally prefer using Xcode on Mac OS X, Code::Blocks on Windows, and Anjuta C/C++, KDevelop, or Gedit on Linux, but it is all a matter of personal preference.

# Customizing the Template #
At the top of the top-level "CMakeLists.txt" file you will find:

```
PROJECT (projectname)
SET (APPLICATION_NAME "Project Name")
SET (APPLICATION_CODENAME "${PROJECT_NAME}")
SET (APPLICATION_COPYRIGHT_YEARS "2009")
SET (APPLICATION_VERSION_MAJOR 1)
SET (APPLICATION_VERSION_MINOR 0)
SET (APPLICATION_VERSION_PATCH 0)
SET (APPLICATION_VERSION_TYPE SNAPSHOT)
SET (APPLICATION_VERSION_STRING "${APPLICATION_VERSION_MAJOR}.${APPLICATION_VERSION_MINOR}.${APPLICATION_VERSION_PATCH}-${APPLICATION_VERSION_TYPE}")
SET (APPLICATION_VENDOR_ID "com.yourcompany")
SET (APPLICATION_VENDOR_NAME "Your Company")
SET (APPLICATION_VENDOR_URL "yourcompany.com")
SET (APPLICATION_ID "${APPLICATION_VENDOR_ID}.${PROJECT_NAME}")
```

You should replace all instances of "projectname" with your project's POSIX name and all instances of "Project Name" with your project's pretty name (i.e. title or display name). You should replace "com.yourcompany" with the reverse-domain of your company (or of the location where the project is being hosted... such as "com.google.code"). Replace "Your Company" with the name of your company (or of the hosting service such as "Google Code").

# Implementing the Commandline Main #
There are three types of main routines that this project supports:

  * Commandline main
  * Interactive main
  * Graphical main

Both the commandline and interactive main use STDIN (std::cin) and STDOUT (std::cout) for input and output; however, the commandline variant should expect all the necessary information to be provided in the commandline invocation whereas the interactive variant should prompt the user for any required information that has not been provided. The graphical main uses a Qt GUI to interact with the user.

By default, the commandline main is used. The interactive main may be invoked by passing the argument "--interactive" on the commandline. The GUI main may be invoked by passing the "--gui" argument on the commandline.

Implementing the commandline main involves:
  * Adding member variables to "App" in "src/app.h" to reflect any additional commandline arguments that your program will accept.
  * Augmenting "App::App(int argc, char`*``*` argv)" in "src/app.cpp" to handle any additional commandline arguments that your program accepts and to store their values in the added member variables.
  * Updating "App::printHelpMessage()" in "src/app.cpp" to print the added commandline parameters and what those parameters mean.
  * Replacing the body of "App::consoleMain()" in "src/app.cpp" to use the commandline parameters and generate the necessary output.

Your implementation of "App::consoleMain()" should cause the program to terminate with an error if the necessary parameters have not been passed on the commandline.

# Implementing the Interactive Main #
Implementing the interactive main is identical to implementing the commandline main, except that you should redefine "interactiveMain()" instead of "consoleMain()", and you should prompt the user for any needed input that has not already been given on the commandline, instead of causing the program to terminate with an error.

# Implementing the GUI Main #
Implementing the graphical main involves editing "App::initGUI()" in "src/app.cpp" to setup your application's graphical user interface. A stub/example version of "App::initGUI" that creates a window that displays "Hello world!" has already been created for you. You should look at the [Qt Framework Documentation](http://qt.nokia.com/doc/latest/) for how to construct the GUI application.

Your "initGUI()" function should be sensitive to the commandline parameters accepted by "consoleMain()" and "interactiveMain()", but should use reasonable default values for any parameters that have not been supplied by the user on the commandline.

# Preferences #
The [C++ Project Template](http://code.google.com/p/cpp-project-template/) uses the [QSettings](http://doc.trolltech.com/4.5/qsettings.html) class for loading and storing configuration parameters. The template configures QSettings (or, more accurately, the QCoreApplication class) so that a QSettings object constructed using the default constructor will automatically load/save settings that are particular to your project (using the project identification information in the top-level CMakeLists.txt file).

The project template provides several commandline options for manipulating the project's configuration parameters. The template supports the following commandline options:

  * --prefset _key_=_value_
  * --prefget _key_
  * --prefdel _key_
  * --preflist

The "--prefset" option sets the key _key_ to the value _value_. The "--prefget" option prints the value that was assigned to the given key _key_. The "--prefdel" option deletes the key _key_, and the "--preflist" option prints all keys that have been set, along with their corresponding values. This makes it very easy to test your application with various configuration settings. It is also a good way to add new features to your project, with the "untested" or "experimental" features disabled by default.

To interact with the configuration programmatically, construct an instance of QSettings using the default constructor, and then use the "value()" function to access the value for a given key, and use the "setValue()" function to set the value for a given key. If you invoke "setValue()" be sure to invoke "sync()" to flush/commit the changes.

The configuration keys can be grouped hierarchically. When using the QSettings functions "value()" and "setValue()", you should use a slash (/) to separate groups, as in "x/y/z" (z is a child of y which is a child of x). On the commandline, you may use slashes or dots (i.e. "x/y/z" or "x.y.z") to manipulate the keys. An advantage to using groups is that it is possible to enumerate all elements of a given group. It also is in many ways similar to using namespaces (it is a good idea to assign each component its own group and allow that component to access only the keys within the group that it owns).

# Logging #
The project template automatically checks for the existence of the Log4Cxx library and automatically links the main executable with the Log4Cxx library. It is highly recommended that you use Log4Cxx for your logging needs. See the [Log4Cxx API Reference](http://logging.apache.org/log4cxx/apidocs/) for details on using the Log4Cxx library.

This project contains two commandline options for configuring Log4Cxx:

  * --loglevel _level_
  * --loglevel _class_=_level_

The first invocation sets the level of the root logger to the specified level. The second invocation sets the given class logger to the given level. Valid levels are "all", "trace", "debug", "info", "warn", "error", "fatal", and "off".

This project also sets the default appender and pattern layout. If you would like to change the appender or logging output format, you will need to change a few lines towards the top of the "App::App" constructor in "src/app.cpp".