# C++ Application Project Template #
> NOTE: The [C++ Library Project Template](http://code.google.com/p/cpp-library-project-template/) can be found [here](http://code.google.com/p/cpp-library-project-template/).
Creating a new C++ project from scratch can involve a lot of tedium and overhead. The purpose of this project is to provide a template which can be easily modified to create your own C++ project with minimal effort. Key features of this template include:
  * Use of the CMake build system.
  * Makefile wrapper for invoking CMake.
  * Automatic configuration of files ending in:
    * ".in.h.cmake"
    * ".h.in.cmake"
  * Testing for and linking against the [Boost C++ Libraries](http://www.boost.org/).
  * Testing for and linking against the [Qt4 SDK](http://qt.nokia.com/downloads).
  * Testing for and linking against the [Log4Cxx](http://logging.apache.org/log4cxx/) library.
  * Testing for and using the [UnitTest++](http://unittest-cpp.sourceforge.net/) unit test framework.
  * Standard, GNU-like project structure:
    * README
    * AUTHORS
    * INSTALL
    * ChangeLog
    * LICENSE
    * Makefile
    * src/
    * test/
    * ...
  * Standard, GNU-like project behavior:
    * --version
    * --help
  * Easy listing/editing of application parameters:
    * --prefget
    * --prefset
    * --prefdel
    * --preflist
  * Easy editing of application log levels:
    * --loglevel level
    * --loglevel logger=level
  * Automatic documentation targets
  * Automatic install targets
  * Automatically executes unit tests after build.

This project template is "Public Domain" (Google will list it as licensed under the "New BSD License", simply because Google code does not have a "Public Domain" option). You may do whatever you want with the project template, and if you modify it, you can apply whatever license you want to the modified version (as long as you don't try to take this, original, project template out of the public domain). It would be nice if you would spread the word about this project template and point people to the original source of the project template (maybe give me some credit), but that isn't required. Hopefully this template will save you some time.

## Application vs. Library ##
This [C++ Project Template](http://code.google.com/p/cpp-project-template/) is intended for building a C++ application. To build a C++ library, please use the [C++ Library Project Template](http://code.google.com/p/cpp-library-project-template/).

## Programming Language ##
The [C++ Project Template](http://code.google.com/p/cpp-project-template/) and [C++ Library Project Template](http://code.google.com/p/cpp-library-project-template/) have a corresponding [Java Project Template](http://code.google.com/p/java-project-template/) and [Java Library Project Template](http://code.google.com/p/java-library-project-template/).

## Development Environment Setup ##
Directions for setting up a C/C++ development environment for using this template are given [at this link](http://code.google.com/p/cpp-project-template/wiki/DevelopmentEnvironmentSetup).

## Usage Instructions ##
Complete directions for using and applying this template are given [at this link](http://code.google.com/p/cpp-project-template/wiki/Basics).

## Feedback and Bug Reports ##
Please contact [Michael Aaron Safyan](http://sites.google.com/site/michaelsafyan/) (see the [contact page](https://sites.google.com/site/michaelsafyan/contact)) to send feedback or file a bug report.