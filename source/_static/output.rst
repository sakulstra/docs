Stage "Output"
--------------

At this stage the output files are created from the images and written
to the disk. The resultant images also appear in the central window of
the program.

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Output_main_tab.png
   :alt: 

Unlike the other stages, the "Output" stage becomes available only after
all page pass the stages of "Select Content" and "Page Layout". This is
because the size of pages in the output depend on each other. Say if it
found a big page, then all the other fields are increasing (more is
described in the documentation on the Page Layout stage). Therefore it
is important to know the final size of pages, and it can only be done
through the stages of "Select Content" and "Page Layout". Why stage is
the "Select Content" stage necessary? Because all options under "Page
Layout" are set manually, or default values are taken.

Configure the following:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Output_param_dpi_tab-en.png
   :alt: 

*Output Resolution (DPI)* - you can manually specify a resolution for
the output files:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Output_dpi_win-en.png
   :alt: 

Please note that although asymmetric DPI is currently supported
(horizontal and vertical DPI is not equal), this may be withdrawn at
some stage.

The default is 600 DPI. In some cases it is 300.

*Mode* - Selects the output mode of the pages:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Output_param_rezhim_tab-en.png
   :alt: 

**Black and White** mode hardly requires explanation but clearly there
are no greytones available so this would not be suitable for any images
and some drawings. There is an option to "despeckle", and to increase or
decrease the line thickness (i.e. of the text). In general it is best to
not despeckle if the image is reasonably clean as despeckling can result
in the loss of some portions of text. This may be compensated for to a
degree by increasing the line thickness but it's probably important to
experiment on a few pages before applying to the entire project.

The option **Color / Grayscale** has additional settings that are
available:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Output_param_rezhim_color_tab-en.png
   :alt: 

Margins can be filled with white or left as is. If the margins are
filled in white, then the option to equalise lighting also becomes
available. This option normalizes the background color, bringing it to
white, and normalizes contrast, increasing it in the shaded areas.

**Mixed mode** is used for projects in which there are scans from
half-tone images (grayscale or color). Pictures will be automatically
detected and displayed as it is, just as in the "Colour / Gray" with the
included equalised illumination. The rest of the page is displayed in
black and white.

Automatic image works well enough, but if the picture merges smoothly
into the background the result may be unsatisfactory. In this case, you
must create and configure the picture zone images. It is important to
note that the creation of zones of images is possible only in mixed
mode.

Display all files at once
-------------------------

To do this, run batch processing through the menu. The files will be
stored in the directory you chose when you created the project.
Unfortunately, unlike other stages, already derived pages will be
displayed again, even if nothing in them has changed. This feature will
be removed in future versions. In the meantime, if necessary, tweak a
few pages after the running of a batch, it is better not to run the
entire batch processing again, rather adjust the few pages by hand. The
process of withdrawal of the current page begins immediately at the
transition to the stage of "withdrawal" or when moving to another page
at this point.

The format of output files
~~~~~~~~~~~~~~~~~~~~~~~~~~

Output is in TIFF format. We're using
`LZW <http://en.wikipedia.org/wiki/Lempel%E2%80%93Ziv%E2%80%93Welch>`__
to ensure lossless compressed images.

`Back to the user manual <User-Guide>`__

Links to all other stages:
~~~~~~~~~~~~~~~~~~~~~~~~~~

`Fix Orientation <Fix-Orientation>`__

`Split Pages <Split-Pages>`__

`Deskew <Deskew>`__ (correcting tilted pages)

`Select Content <Select-Content>`__

`Page Layout <Page-Layout>`__
