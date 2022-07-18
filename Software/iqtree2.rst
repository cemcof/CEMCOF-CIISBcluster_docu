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
   $ # OpenMP
   $ iqtree2 -T 4 -s example.phy
   $ # OpenMPI
   $ module add openmpi/4.1.2/m64-deb10/para
   $ mpirun -np 4 iqtree2-mpi -T 2 ...
   
* Version 2.2.0 is a pre-release version and is not compiled with support for OpenMPI
* Example input data are in ``/cemcofsw/bioinf/iqtree2/VERSION/m64-deb10/para/``

**DEVELOPER TUTORIAL/HELP PAGES**

* `Github <https://github.com/iqtree/iqtree2>`_
* `Web Pages <http://www.iqtree.org/>`_
* `Web Service <http://iqtree.cibiv.univie.ac.at>`_
* `User Support <https://groups.google.com/d/forum/iqtree>`_

**REFERENCES**

* S. Kalyaanamoorthy, B.Q. Minh, T.K.F. Wong, A. von Haeseler, L.S. Jermiin (2017) ModelFinder: Fast model selection for accurate phylogenetic estimates. *Nat. Methods*, 14:587-589. https://doi.org/10.1038/nmeth.4285

When performing tree reconstruction please cite:

* L.-T. Nguyen, H.A. Schmidt, A. von Haeseler, and B.Q. Minh (2015) IQ-TREE: A fast and effective stochastic algorithm for estimating maximum likelihood phylogenies. *Mol. Biol. Evol.*, 32, 268-274. https://doi.org/10.1093/molbev/msu300

For the ultrafast bootstrap (UFBoot) please cite:

* D.T. Hoang, O. Chernomor, A. von Haeseler, B.Q. Minh, and L.S. Vinh (2017) UFBoot2: Improving the ultrafast bootstrap approximation. *Mol. Biol. Evol.*, in press. https://doi.org/10.1093/molbev/msx281

When using posterior mean site frequency model (PMSF) please cite:

* H.C. Wang, B.Q. Minh, S. Susko, A.J. Roger (in press) Modeling site heterogeneity with posterior mean site frequency profiles accelerates accurate phylogenomic estimation. *Syst. Biol.* https://doi.org/10.1093/sysbio/syx068

When using partition models please cite:

* O. Chernomor, A. von Haeseler, B.Q. Minh (2016) Terrace aware data structure for phylogenomic inference from supermatrices. *Syst. Biol.*, 65:997-1008. https://doi.org/10.1093/sysbio/syw037

When using polymorphism-aware models please cite:

* D. Schrempf, B.Q. Minh, N. De Maio, A. von Haeseler, C. Kosiol (2016) Reversible polymorphism-aware phylogenetic models and their application to tree inference. *J. Theor. Biol.*, 407:362-370. https://doi.org/10.1016/j.jtbi.2016.07.042
