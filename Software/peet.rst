.. peet:

PEET
---------

**VERSIONS:**

* 1.15.0

**GENERAL INFORMATION**

*"PEET (Particle Estimation for Electron Tomography) is an open-source package for aligning and averaging particles in 3-D subvolumes extracted from tomograms. It seeks the optimal alignment of each particle against a reference volume through several iterations. If PEET and IMOD are both installed, most PEET operations are available from the eTomo graphical user interface in IMOD. PEET uses the parallel processing framework within IMOD, so that the lengthy computations can be distributed to multiple cores on one computer, to a set of linked workstations, or to a cluster. PEET is written in Matlab and a compiled version is distributed along with the Matlab runtime environment needed to run it."* 

**USAGE SPECIFIC INFORMATION**

* works together with IMOD which uses Python 3.8 and CUDA 11.2

.. code-block:: console

   ssh ciisb.ceitec.muni.cz
   module add imod
   module add peet

**DEVELOPER TUTORIAL/HELP PAGES**

* documentation_
* `IMOD/PEET workshop`_

.. _documentation: https://bio3d.colorado.edu/ftp/PEET/man/html/index.html
.. _IMOD/PEET workshop: https://bio3d.colorado.edu/RML_2017/2017_IMOD_PEET_Workshop/index.html
