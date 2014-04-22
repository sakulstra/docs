At this stage it is possible to turn scans by multiples of 90 degrees.
i.e., to correct sideways or upside-down scans.

This is a manual stage because the program does not know how to
determine the correct orientation of scans - the user must do this. This
also means that using batch processing at this stage is useless.
Obviously it behooves the user to make sure all initial scans are of the
same orientation, if possible; mixing orientation will make this stage
less automatic and more time-consuming.

Panel settings for this stage appears as follows:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Orient_param_tab-en.png
   :alt: 

Rotate
------

Buttons with yellow arrows rotate scans 90 degrees in one direction or
the other. A green pointer shows which direction the scan is oriented at
the given moment. The button "reset" returns the scan to the initial
position - the green pointer will indicate upward.

Apply to
--------

This makes it possible to turn not only this page (which is done
automatically), but also others. This dialogue is opened by clicking on
the "Apply to ..." button and it appears as follows:

.. figure:: https://github.com/scantailor/scantailor/wiki/images/Orient-en.png
   :alt: 

The first two options in the list do not require explanation. “This page
and the following ones” will apply the same operation that has been
applied to the current page to each page after the current one. “Every
other page” will apply rotation to either each even or to each odd page
in accordance with whether the current page is even or odd. The last two
options are activated only if two or more pages are selected from the
preview pane. To use “Every other selected page” the selected pages must
be continuous. To select continuous pages it's often more convenient to
use Shift + click.

`Back to the user manual <User-Manual>`__

`Go to the next stage <Split-Pages>`__

Links to all other stages:
--------------------------

`Fix Orientation <Fix-Orientation>`__

`Split Pages <Split-Pages>`__

`Deskew <Deskew>`__ (correcting tilted pages)

`Select Content <Select-Content>`__

`Page Layout <Page-Layout>`__
