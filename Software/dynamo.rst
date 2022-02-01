.. dynamo:

DYNAMO
---------

**VERSIONS:**

* 1.1.514

**GENERAL INFORMATION**

*"Dynamo is a software environment for subtomogram averaging of cryo-EM data."* The package is developed and maintained by `Daniel Castano-Diez`_.

**USAGE SPECIFIC INFORMATION**

* uses CUDA 11.2 and the Matlab MCR

.. code-block:: console

   ssh ciisb.ceitec.muni.cz
   module add dynamo

* in order to use autoalign_dynamo_ from Alister Burt (works with Matlab not MCR) do following

.. code-block:: console

   ssh ciisb.ceitec.muni.cz
   module add matlab
   module add imod
   matlab
   run /cemcofsw/em/dynamo/1.1.514/dynamo_activate.m
   run /cemcofsw/em/dynamo/site-packages/autoalign_dynamo/bin/autoalign_activate.m

**DEVELOPER TUTORIAL/HELP PAGES**

* documentation_
.. _Daniel Castano-Diez: https://www.c-cina.org/stahlberg/team/daniel-castano-diez/
.. _autoalign_dynamo: https://github.com/alisterburt/autoalign_dynamo
.. _documentation: https://bio3d.colorado.edu/imod/
