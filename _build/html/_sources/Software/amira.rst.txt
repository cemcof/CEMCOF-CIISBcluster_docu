.. amira:

AMIRA
---------

**VERSIONS:**

* 2020.2
* 2021.1

**GENERAL INFORMATION**

Amira is a program for interactive visual data analysis not only of 3D electron microscopy data but also other imageing data. In case of electron microscopy, it is primarily used for volume segmentation.

**USAGE SPECIFIC INFORMATION**

.. warning::
   |under_construction| currently does not run in graphical mode on the computational nodes

.. code-block:: console

   ssh -X ciisb.ceitec.muni.cz
   qsub -I -select=1:ncpus=4:ngpus=1:mem=48gb -l walltime=4:00:00
   module add amira


**DEVELOPER TUTORIAL/HELP PAGES**

* documentation_

.. |under_construction| image:: ../oblasky/underConstruction_thumbnail.png
.. _documentation: https://assets.thermofisher.com/TFS-Assets/MSD/Product-Guides/users-guide-amira-software-2019.pdf
