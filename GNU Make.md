گنو میک
گنو میک is a tool which controls the generation of executables and other non-source files of a program from the program's source files.

Make gets its knowledge of how to build your program from a file called the makefile, which lists each of the non-source files and how to compute it from other files. When you write a program, you should write a makefile for it, so that it is possible to use Make to build and install the program.

Capabilities of Make
Make enables the end user to build and install your package without knowing the details of how that is done -- because these details are recorded in the makefile that you supply.
Make figures out automatically which files it needs to update, based on which source files have changed. It also automatically determines the proper order for updating files, in case one non-source file depends on another non-source file.
As a result, if you change a few source files and then run Make, it does not need to recompile all of your program. It updates only those non-source files that depend directly or indirectly on the source files that you changed.

Make is not limited to any particular language. For each non-source file in the program, the makefile specifies the shell commands to compute it. These shell commands can run a compiler to produce an object file, the linker to produce an executable, ar to update a library, or TeX or Makeinfo to format documentation.
Make is not limited to building a package. You can also use Make to control installing or deinstalling a package, generate tags tables for it, or anything else you want to do often enough to make it worth while writing down how to do it.
Make Rules and Targets
A rule in the makefile tells Make how to execute a series of commands in order to build a target file from source files. It also specifies a list of dependencies of the target file. This list should include all files (whether source files or other targets) which are used as inputs to the commands in the rule.

Here is what a simple rule looks like:

target:   dependencies ...
          commands
          ...
When you run Make, you can specify particular targets to update; otherwise, Make updates the first target listed in the makefile. Of course, any other target files needed as input for generating these targets must be updated first.

Make uses the makefile to figure out which target files ought to be brought up to date, and then determines which of them actually need to be updated. If a target file is newer than all of its dependencies, then it is already up to date, and it does not need to be regenerated. The other target files do need to be updated, but in the right order: each target file must be regenerated before it is used in regenerating other targets.

Advantages of GNU Make
GNU Make has many powerful features for use in makefiles, beyond what other Make versions have. It can also regenerate, use, and then delete intermediate files which need not be saved.

GNU Make also has a few simple features that are very convenient. For example, the -o file option which says ``pretend that source file file has not changed, even though it has changed.'' This is extremely useful when you add a new macro to a header file. Most versions of Make will assume they must therefore recompile all the source files that use the header file; but GNU Make gives you a way to avoid the recompilation, in the case where you know your change to the header file does not require it.

However, the most important difference between GNU Make and most versions of Make is that GNU Make is free software.

Makefiles And Conventions
We have developed conventions for how to write Makefiles, which all GNU packages ought to follow. It is a good idea to follow these conventions in your program even if you don't intend it to be GNU software, so that users will be able to build your package just like many other packages, and will not need to learn anything special before doing so.

These conventions are found in the chapter ``Makefile conventions'' (147 k characters) of the GNU Coding Standards (147 k characters).

Downloading Make
Make can be found on the main GNU ftp server: http://ftp.gnu.org/gnu/make/ (via HTTP) and ftp://ftp.gnu.org/gnu/make/ (via FTP). It can also be found on the GNU mirrors; please use a mirror if possible.

Documentation
Documentation for Make is available online, as is documentation for most GNU software. You may also find more information about Make by running info make or man make, or by looking at /usr/share/doc/make/, /usr/local/doc/make/, or similar directories on your system. A brief summary is available by running make --help.

Mailing lists
Make has the following mailing lists:

bug-make is used to discuss most aspects of Make, including development and enhancement requests, as well as bug reports.
help-make is for general user help and discussion.
Announcements about Make and most other GNU software are made on info-gnu (archive).

Security reports that should not be made immediately public can be sent directly to the maintainer. If there is no response to an urgent issue, you can escalate to the general security mailing list for advice.

Getting involved
Development of Make, and GNU in general, is a volunteer effort, and you can contribute. For information, please read How to help GNU. If you'd like to get involved, it's a good idea to join the discussion mailing list (see above).

Test releases
Trying the latest test release (when available) is always appreciated. Test releases of Make can be found at http://alpha.gnu.org/gnu/make/ (via HTTP) and ftp://alpha.gnu.org/gnu/make/ (via FTP).
Development
For development sources, issue trackers, and other information, please see the Make project page at savannah.gnu.org.
Translating Make
To translate Make's messages into other languages, please see the Translation Project page for Make. If you have a new translation of the message strings, or updates to the existing strings, please have the changes made in this repository. Only translations from this site will be incorporated into Make. For more information, see the Translation Project.
Maintainer
Make is currently being maintained by Paul Smith. Please use the mailing lists for contact.
Licensin
Make is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.
