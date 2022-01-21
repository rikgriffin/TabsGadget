# TabsGadget
Toolbox Tabs gadget for RISC OS

Welcome to the open source release of the Tabs Toolbox gadget.

I've uploaded the source to github using a RISC OS style directory structure (eg ".c" files are in a directory called "c"), and LanManFS style file names (eg an Obey file will be called "file,feb"). My assumption is that anyone downloading from github will be doing so on Windows/Linux and then transferring the files to RISC OS using SMB of some sort. If you download a ZIP of the entire source tree, then extract it on the Windows/Linux side before copying files to RISC OS, then LanManFS will get the correct file types.

Build instructions:

Tabs was written using the Acorn (later ROOL) development environment, and the Norcroft compiler. It needs the standard C library, the Toolbox library and "glib" - both the header files for compilation and the libraries to link against.

There used to be a dependency on an ancient product called "Dr Smith's C Development Toolkit" which was something like "valgrind" for RISC OS. But for this final release I've commented out any dependencies on that product, so you should be able to compile the module with just a standard "Acorn C/C++" development environment.

I've never tried building this under any other environment, or with any other compiler, but I'm sure someone will make that work!

To build, just run the "Make" obey file. This just runs "amu all" in a TaskWindow. There's a pretty standard Makefile that you can probably use with some other make utility if you wish.

Note that to run "make clean", you need an "rm" command on your Run$Path which behaves similarly to the unix/linux "rm". You also need a "trim" command which is used to snip off the "Dynamic dependencies" part of the Makefile. I'll upload BASIC version of these commands to github, but someone will probably come up with a better system.

Also note that you may need to create a directory called "o" for the compiler to put object files in to - this directory exists in the repo but seems to get lost if you download a ZIP archive.

Rik Griffin Jan 2022



Known issues in this version:

Events on a nested window return the wrong parent_object in the IDBlock,
but the correct parent_component.


Licence
~~~~~~~

Copyright 2003-2022 Rik Griffin <rik.grf@gmail.com>
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

   1. Redistributions of source code must retain the above copyright
      notice, this list of conditions and the following disclaimer.

   2. Redistributions in binary form must reproduce the above copyright notice,
      this list of conditions and the following disclaimer in the documentation
      and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY R GRIFFIN "AS IS" AND ANY EXPRESS
OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL R GRIFFIN OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY
OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH
DAMAGE.
