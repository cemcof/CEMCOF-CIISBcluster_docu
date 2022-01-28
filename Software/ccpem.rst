.. ccpem:

CCPEM
-----

**VERSIONS:**

* 1.5.0

**GENERAL INFORMATION**

A collection of programs for structure refinement, model docking, or model building. Contains programs such as *Coot*, *REFMAC*, *Flex-EM*, etc.

**USAGE SPECIFIC INFORMATION**

* do not run the heavy load GUI applications on the frontend

.. code-block:: console

   ssh -X ciisb.ceitec.muni.cz
   qsub -I -l select=1:ncpus=4:ngpus=1:mem=48gb -l walltime=4:00:00
   module add ccpem


**DEVELOPER TUTORIAL/HELP PAGES**

* documentation_

.. _documentation: https://www.ccpem.ac.uk/download.php
