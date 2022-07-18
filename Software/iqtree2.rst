.. iqtree2:

IQ-TREE
---------

**VERSIONS:**

* 2.1.2
* 2.2.0

**GENERAL INFORMATION**

Efficient and versatile phylogenomic software by maximum likelihood `http://www.iqtree.org <http://www.iqtree.org>`_.

**USAGE SPECIFIC INFORMATION**

.. code-block:: console

   $ ssh ciisb.ceitec.muni.cz
   $ module add iqtree2
   $ # penMP
   $ iqtree2 -T 4 -s example.phy
   $ # OpenMPI
   $ module add openmpi/4.1.2/m64-deb10/para
   $ mpirun -np 4 iqtree2-mpi -T 2 ...
   
* Version 2.2.0 is a pre-release version and is not compiled with support for OpenMPI

**DEVELOPER TUTORIAL/HELP PAGES**

* `github <https://github.com/iqtree/iqtree2>`_