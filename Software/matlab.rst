.. matlab:

Matlab
---------

**VERSIONS:**

* R2021a

**GENERAL INFORMATION**

MATLAB - programming and numeric conputing platform for data analysis, algorithm development, and model creation

**USAGE SPECIFIC INFORMATION**

* use the interactive session start computationally intensive jobs

.. code-block:: console

   ssh -X ciisb.ceitec.muni.cz
   qsub -I -l select=1:ncpus=4:ngpus=1:mem=24gb -l walltime=2:00:00
   module add matlab

**DEVELOPER TUTORIAL/HELP PAGES**

* link_
.. _link: https://www.mathworks.com/help/matlab/getting-started-with-matlab.html
