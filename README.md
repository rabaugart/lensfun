Changes
-------

Sony alpha 7M3 backported

WHAT IS IT
----------

The goal of the Lensfun library is to provide a open source database
of photographic lenses and their characteristics. In the past there
was a effort in this direction (see http://www.epaperpress.com/ptlens/),
but then author decided to take the commercial route and the database
froze at the last public stage. This database was used as the basement
on which Lensfun database grew, thanks to PTLens author which gave his
permission for this, while the code was totally rewritten from scratch
(and the database was converted to a totally new, XML-based format).

The Lensfun library not only provides a way to read the database
and search for specific things in it, but also provides a set of
algorithms for correcting images based on detailed knowledge of
lens properties. Right now Lensfun is designed to correct
distortion, transversal (also known as lateral) chromatic aberrations,
and vignetting.

The interface is defined both using C++ style and plain C.
The C interface is a wrapper around the C++ classes.

Website: http://lensfun.sourceforge.net/  
Sourceforge: http://sourceforge.net/projects/lensfun/  


LICENSE
-------

The libraries which are part of this package are licensed under the terms
of the GNU Lesser General Public License, version 3. Libraries are located
under the subdirectory libs/ of the source package. A copy of the license
is available in the file lgpl-3.0.txt which can be found in the source
archive. You can read it here: http://www.gnu.org/licenses/lgpl-3.0.html

The documentation files, including those autogenerated with Doxygen,
are covered as well by GNU Lesser General Public License, version 3.

Applications which are part of this package are licensed under the terms
of the GNU General Public License, version 3. Applications are located
under the apps/ subdirectory of the source package. A copy of the license
can be found in the file gpl-3.0.txt which can be found in the source
archive. You can read it here: http://www.gnu.org/licenses/gpl-3.0.html

Also the build system (the contents of the build/ subdirectory plus the
ac.py file) is licensed under GPL v3.

Test programs and tools are put into public domain, unless explicitly
specified otherwise in the header of the source files. Test programs
are located under the tests/ subdirectory, and tools are located in tools/.

The lens database is licensed under the Creative Commons Attribution-Share
Alike 3.0 license. The database is located under the data/ subdirectory
of the source package. You can read it here:
http://creativecommons.org/licenses/by-sa/


BUILD INSTRUCTIONS
------------------

The build system is based on CMake (http://www.cmake.org/). In order to 
successfully configure and build the project the following tools are more 
or less required:

 - CMake 
 - GNU Make 
 - Doxygen in order to generate the library documentation.
 - GLib 2.0 and later which is used for low-level I/O and XML parsing.
 - libpng is required to build and run test programs.

First enter the Lensfun root folder and create a build directory.

    cd lensfun
    mkdir cmake_build

Enter the build directory and run CMake to configure your sources and create 
the build files

    cd cmake_build
    cmake ../
    
Run make/make install as usual
    
    make
    make install

The following CMake options can be set (defaults are upper case):

    -DCMAKE_BUILD_TYPE=DEBUG|Release        select debug or release build mode
    -DINSTALL_HELPER_SCRIPTS=off|ON         install various helper scripts
    -DCMAKE_INSTALL_PREFIX=/USR/LOCAL       install prefix 

    -DBUILD_STATIC=OFF|on       build static or shared lib
    -DBUILD_TESTS=OFF|on        build also the test programs
    -DBUILD_LENSTOOL=OFF|on     build Lensfun reference implementation
    -DBUILD_FOR_SSE=off|ON      build with SSE optimisation
    -DBUILD_FOR_SSE2=off|ON     build with SSE2 optimisaiton
    -DBUILD_DOC=OFF|on          build documentation

If you want to have more detailed output when running 'make' you can simply add 
'VERBOSE=1' to the make command line.

You can also build packages with cmake:

    Add -DCPACK_BINARY_DEB:BOOL=ON or -DCPACK_BINARY_RPM:BOOL=ON to the
    command line and then "make package". (But this is not extensively tested.)

Please note that running cmake again does NOT reset all options to default or 
reconfigure all variables. To restart with a clean configuration delete all files
in your cmake_build folder.

If you prefer setting the configuration with a GUI or want to get an extensive 
overview of all available settings and cache values run cmake-gui.


DOCUMENTATION
-------------

The end-user documentation for the library can be built by issuing the
command:

    make docs

Also you can read it online at any time by pointing your browser to:

	http://lensfun.sourceforge.net/manual/

The documentation on the site is updated every night from Git, so it always
contains the latest info on the library.


CREDITS
-------

Here goes a full list of people who have contributed to this library:

CODE:
  > Andrew Zabolotny <zap@homelink.ru>
 
LENS DATA:
  > Tom Niemann: original open-source ptlens database.

THANKS:
  > Pablo d'Angelo for the idea of a open-source lens database.
  > 
  > The whole PanoTools team, for all math and knowledge I have borrowed from PanoTools:
  > 
  > Helmut Dersch - The father of most (all?) open-source panorama creation tools.
  > Daniel M. German
  > Kevin Kratzke
  > Rik Littlefield
  > Fulvio Senore
  > Jim Watters
  > Thomas Rauscher
  > Pablo d'Angelo (thanks once more :)
  > Bret McKee
  > Robert Platt

Also I would like to thank the people that made valuable contributions to Lensfun:
  > Niels Kristian Bech Jensen
  > Pascal de Bruijn
  > Thomas Modes
  > Torsten Bronger

And of course great thanks to all the people sending profiles for the database. 
