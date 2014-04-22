About
-----

Scan Tailor is an interactive tool for post-processing of scanned pages.
It gives the ability to cut or crop pages, compensate for skew angle,
and add / delete content fields and margins, among others. You begin
with raw scans, and end up with tiff's that are ready for printing or
assembly in PDF or DjVu file.

Scanning, OCR, and the building of single-file multi-page documents are
not included in the project objectives.

The program is developed for Windows, GNU / Linux, and other Unix-like
systems such as Mac OS X.

Installation and first start
----------------------------

For Windows
~~~~~~~~~~~

Versions for Windows come in the form of an installer. Install the
program and run through the self-explanatory menu.

For GNU / Linux and Mac OS X
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If your distribution does not have Scan Tailor in its repositories (and
the only distribution I know of is Alt Linux), then you have to `build
it from source <Building-from-Source-Code-on-Linux-and-Mac-OS-X>`__.
After assembly, you can run Scan Tailor via Alt + F2, using the command
"scantailor" (without the quotes), or if you don't have a Gnome
environment you can type the same command on the command line. On Mac OS
X, it currently must be run from the terminal after building and
installation.

Once launched, the main program window looks like this:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/First_start-en.png
   :alt: 

In the central panel we see the items "New project ...", " Open Project
... " and a list of recent projects, if any.

Create Project
--------------

So, let's create our first project. First, we need the raw material -
Scan Tailor requires the presence of at least one image file in the
project. This source material can be scanned or photographed pages of a
book or a magazine. Follow these `tips for
scanning <Tips-for-Scanning>`__ to get the best results.

Click on "New Project ..." - Opens dialog "Project Files".

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Begin_files-en.png
   :alt: 

"Input Directory" - the folder where the original scans are located.

"Output Directory" - the folder where processed scans are stored.

"Files Not In Project" - files in a folder specified in the Input
Directory, but not yet added to the project or files that were added and
have been removed from the project.

"Files In Project"- files added to the project, although not necessarily
from the directory entry. The project can take files from different
directories to contribute to the project. You may select files from one
directory, then change it, select files from there, and so on.

The buttons ">>" and "<<" between "Files Not In Project" and "Files In
Project" move files from one list to another. This will only move
highlighted files. It is possible to highlight all the files via "Select
All", or individually - via Ctrl + Click, or a range - through Shift +
Click as per standard selection procedures.

Once you've selected the files to use in the project (supported files
types are *.tif, *.tiff, *.png, *.jpg, \*.jpeg), click OK. Usually at
this stage the process of creating the project ends, but if project
files with an unspecified or clearly incorrect DPI have been selected
then a "Fix DPI" dialogue window will open.

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Fix_dpi-en.png
   :alt: 

To explain a little about DPI; DPI stands for "dots per inch" ("dots per
inch) which defines the correspondence between the physical dimensions
(inches, centimeters), and pixel size. Pixels are the points which make
up digital images. For example in the screenshot above, we see two scans
with the size of 2816 x 2112 pixels. If we knew the DPI of the scan, we
could calculate their physical size. If for example, assume that their
DPI was 300x300 (300 horizontal by 300 vertical), then the physical
dimensions are:

(2816 / 300) x (in 2112 / 300) = 9,4 x 7 inches = 23,8 x 17,8 cm

In this case DPI is determined by the scan settings, and usually
scanning software produces files of the correct DPI. However during
further manipulation of the image this can easily get lost so it must be
restored to normal for operation with Scan Tailor. The most common DPI's
are 300 and 600. Horizontal and vertical components of the DPI are
usually the same.

For digital camera images you may need to measure the physical
dimensions of the area of which the picture was taken then divide the
number of pixels along that dimension of the image by the length in
inches to obtain the DPI (dots or pixels per inch). Keep this in mind
before you get rid of a book, though you can often look up a book's
physical dimensions online. DPI numbers below 150 will generally not
lead to satisfactory results.

Consider again the dialogue window "Fix DPI". The tab "Need Fixing"
lists only those files in which the DPI is not specified or is clearly
wrong. In the tab "All Pages" (Not to be confused with the same
drop-down list) lists all the files at all. They also can change the
DPI. If we know that all the files in the project are 300 x 300 DPI,
then one can go to set the DPI for all files. To do this, highlight the
row that says "All pages" with the triangle/arrow next to it (not the
tab that says All pages), select the correct DPI, and click apply. You
can also specify the DPI for groups of files with the same pixel size,
and also for individual files. Files that have been fixed disappear from
the tab "Need Fixing". When the tab is completely empty, click OK. Upon
clicking OK, the process of creating the project will be completed.

The DPI settings which you specify are not written to the files - they
are only stored in the Scan Tailor project file.

At the stages of processing "Correction orientation" and "Cutting pages"
you have the ability to add / remove files from the project with the
help of a pop-up menu, selected via a right click of the mouse in the
preview window (the small thumbnails):

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Lenta_popup_menu-en.png
   :alt: 

When you try to add a file with invalid DPI Scan Tailor will ask you to
fix it:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Change_dpi_one_file-en.png
   :alt: 

Keep in mind that there is currently no way to change the DPI for a file
in the already created project, or any way to add a group of files to an
existing project. This feature is expected in future versions.

The concept of processing scans in Scan Tailor
----------------------------------------------

First, you need to understand the general concept of the program.
Processing of the scanned pages in Scan Tailor is like a factory
conveyor. There are stages, each of which deals with some specific
manipulation of the image to produce the final product.

Let's look at the main program window:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Tailor_win.png
   :alt: 

Top left we have a list of stages (1), and a preview window (4) it can
thus be considered a pipeline. It is important to understand that as per
a regular assembly line if the product reached a certain stage, then all
the previous stages must have been completed in strict sequence. At any
time you can return to one of the previous stages to see, and if
necessary to correct, the operation that was done to the image at this
point.

The round button "Play" to the right of the name of each stage runs the
batch processing, like starting the above described conveyor. Pressing
the "Play" button causes pages, one by one, to pass through all stages
of processing, including the current stage. "Pass through all stages of
processing" - does not necessarily mean "processed". For example if the
scan had already been cut, then when it gets to the stage of cutting
again it will not be cut, unless you had changed something important
such as its orientation. You may stop batch processing at any stage by
using the large round "stop" button during the processing of the main
work area (3).

None of the stages, except the last stage, named "Output" actually
record the resulting image to the disk. All stages except the last are
purely analytical.

The rest of the main window:

(2) Options for the current processing stage.
(3) Main working area that displays the current image, as well as tools
    for manipulating it,
(4) Tool tips - here you can see prompts for how to use the tool or item
    under the mouse pointer.
(5) a button to "Keep the active page in the field of view." In the
    depressed condition this causes the program to maintain the active
    page in the preview window (4).

Program menu
------------

File menu
~~~~~~~~~

::

    Menu Item       | Shortcut|

+-----------------------+----------+
| New Project ...       | Ctrl+N   |
+-----------------------+----------+
| Open Project ...      | Ctrl+O   |
+-----------------------+----------+
| Save Project          | Ctrl+S   |
+-----------------------+----------+
| Save Project As ...   |          |
+-----------------------+----------+
| Close Project         | Ctrl+W   |
+-----------------------+----------+
| Quit                  | Ctrl+Q   |
+-----------------------+----------+

These are mostly self-explanatory, except for the item "Close Project".
This command closes the project, but not the whole program. The main
window returns to the way it was immediately after starting the program.
The shortcut keys are listed to the right of the item in the file menu.
For example pressing and holding the control key and then s will save
the project.

Tools Menu:
~~~~~~~~~~~

Debug mode is intended only for developers. After processing a single
page, in the central area of the tabs will appear the intermediate
results of processing.

Processing stages
-----------------

`Fix Orientation <Fix-Orientation>`__

`Split Pages <Split-Pages>`__

`Deskew <Deskew>`__ (correcting tilted pages)

`Select Content <Select-Content>`__

`Page Layout <Page-Layout>`__

See also
--------

`Video Tutorial <http://vimeo.com/12524529>`__
