Building on Linux
-----------------

Prerequisites
~~~~~~~~~~~~~

All requisites should be available for your distribution. The most
important are: \* The basic program build tools. On Ubuntu and Debian
these are available in the meta-package build-essential. On other
distributions, you may need to install the GNU C++ compiler separately.
The package is going to have c++ or g++ in its name. If you can't find
the equivalent of build-essential meta-package for your distribution, be
sure to install the "make" utility as well. \* CMake, the cross platform
build system. \* Qt version 4.4.0 or higher. If you have KDE 4.1 or
later installed then you will have the runtime libraries but you may
have to install the header files and utilities. These are in the package
libqt4-dev on Ubuntu and Debian. Generally, developer packages have the
-dev or -devel suffix. \* Several more developer packages:

These are the package names on Debian and Ubuntu, find the similar ones
for your distribution.

+--------------+-----------+-----------------------------------+
| Package      | Version   | Possible Package Names            |
+==============+===========+===================================+
| libjpeg      | any       | libjpeg62-dev                     |
+--------------+-----------+-----------------------------------+
| zlib         | any       | zlib1g-dev                        |
+--------------+-----------+-----------------------------------+
| libpng       | any       | libpng12-dev                      |
+--------------+-----------+-----------------------------------+
| libtiff      | any       | libtiff4-dev                      |
+--------------+-----------+-----------------------------------+
| libboost     | >= 1.35   | libboost1.40-all-dev              |
+--------------+-----------+-----------------------------------+
| libxrender   | any       | libxrender-dev libXrender-devel   |
+--------------+-----------+-----------------------------------+

Configuration
~~~~~~~~~~~~~

Open a console window and go to the directory that contains the
scantailor sources. From there, run the following (notice the dot at the
end):

.. raw:: html

   <pre>cmake .</pre> 

There will be lots of messages from cmake ending with:

.. raw:: html

   <pre>
   - Configuring done 
   - Generating done
   </pre>

-  If you have missing dependencies you will get an error message
   telling you what is missing. You can then search for the missing
   package and install it.
-  If you have a library and header files installed in a non-standard
   place then cmake will not find them. In that case you can run the
   interactive program '''ccmake''' which allows you to specify paths to
   libraries and header files.

Compilation and Installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <pre>
   make
   sudo make install
   </pre>

Building on Mac OS X
--------------------

MacPorts has already scantailor as a
`package <https://trac.macports.org/browser/trunk/dports/graphics/scantailor/Portfile>`__
(Xcode prerequisites for MacPorts apply)

.. raw:: html

   <pre>
   sudo port selfupdate
   sudo port install scantailor
   </pre>

Building on Mac OS X is very similar to building on Linux but the
package names are different and the MacPorts packaging system needs to
be installed in order to get the needed packages. Also the nonstandard
location that MacPorts installs qmake to needs to be specified.

Prerequisites
~~~~~~~~~~~~~

-  Xcode. Install it either from your Mac OS X install media or better,
   go download the latest version from
   http://developer.apple.com/TOOLS/Xcode/
-  MacPorts. Choose and install the correct dmg version for your version
   of Mac OS X from http://www.macports.org/install.php, then open a
   Terminal window and run:

   .. raw:: html

      <pre>
      sudo port selfupdate
      </pre>

-  Then install the rest of the needed packages with

   .. raw:: html

      <pre>sudo port install cmake qt4-mac-devel boost xrender</pre>

   This installs:
-  CMake, the cross platform build system.
-  Qt version 4.6.0 beta currently
-  Boost version 1.40.0 including libboost
-  libxrender

The rest of the needed packages are installed as dependencies of these.

Configuration
~~~~~~~~~~~~~

Download the scantailor source code package and then upack the source by
entering the following in the directory where the source package
resides:

.. raw:: html

   <pre>tar xf scantailor-0.9.8.1.tar.gz</pre>

Replace the file name above with the name of the version that you have
downloaded. Typing the first few letters of the name and typing tab will
autocomplete the filename for you.

Then navigate to the directory that contains the scantailor sources.
From there, run the following (single line and mind the dot at the end):

.. raw:: html

   <pre>cmake -DCMAKE_LIBRARY_PATH=/opt/local/lib -DCMAKE_INCLUDE_PATH=/opt/local/include
   -DQT_QMAKE_EXECUTABLE=/opt/local/libexec/qt4-mac-devel/bin/qmake .</pre> 

There will be lots of messages from cmake ending with

.. raw:: html

   <pre>
   - Configuring done 
   - Generating done 
   </pre>

-  If you have missing dependencies you will get an error message
   telling you what is missing. You can then search for the missing
   package and install it.
-  If you have a library and header files installed in a non-standard
   place then cmake will not find them. In that case you can specify
   them as above for qmake or run the interactive program '''ccmake'''
   which allows you to specify paths to libraries and header files.

Compilation and Installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <pre>
   make
   sudo make install
   </pre>

