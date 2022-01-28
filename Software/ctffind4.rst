.. ctffind4:

CTFFIND4
--------

**VERSIONS:**

* 4.1.14

**GENERAL INFORMATION**

Command-line based **CPU** program for the determination of the contrast transfer function (CTF) parameters in electron micrographs developed in `Nikolaus Grigorieff lab`_.

**USAGE SPECIFIC INFORMATION**

* will run either from an interactive shell

.. code-block:: console

   module add ctffind4

   ctffind

   Input image file name [input.mrc]     :
   ...
   ...

* or from a source file with a correct structure (see below)

.. code-block:: none

   input.mrc
   output_PW.mrc
   1.34
   300
   2.7
   0.07
   512
   30
   4
   10000
   35000
   500.0
   no
   yes
   yes
   800.0
   no
   no

.. code-block:: console

   module add ctffind4

   ctffind < ctffind.run >> ctffind.log



**DEVELOPER TUTORIAL/HELP PAGES**

* documentation_

.. _Nikolaus Grigorieff lab: https://grigoriefflab.umassmed.edu/
.. _documentation: https://grigoriefflab.umassmed.edu/ctffind4
