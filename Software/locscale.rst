.. locscale:

LOCSCALE
---------

**VERSIONS:**

* 2.0

**GENERAL INFORMATION**

LocScale is a reference-based local amplitude scaling tool using information on expected electron scattering properties of biological macromolecules to improve contrast of cryo-EM density maps.

**USAGE SPECIFIC INFORMATION**

.. code-block:: console

   $ ssh ciisb.ceitec.muni.cz
   $ module add locscale

* **WARNING:** locscale module overrides mpirun command to allow running in parallel. This is because conda environment needs to be activated apriory. Thus, locscale module might interfere with other programs using mpirun and should be used only on its own. For technical details, see file ``/cemcofsw/em/locscale/2.0/x86_64/para/bin/mpirun``.
* For single run:

.. code-block:: console

   $ locscale run_locscale -em path/to/emmap.mrc -mc path/to/model.pdb -res 3 -v -o model_based_locscale.mrc

* For parallel run:

.. code-block:: console

   $ mpirun -np 4 locscale run_locscale -em path/to/emmap.mrc -mc path/to/model.pdb -res 3 -v -o model_based_locscale.mrc -mpi

**DEVELOPER TUTORIAL/HELP PAGES**

* `wiki <https://gitlab.tudelft.nl/aj-lab/locscale/-/wikis/home/>`_
* `gitlab <https://gitlab.tudelft.nl/aj-lab/locscale>`_

**REFERENCES**

* A.J. Jakobi, M. Wilmanns and C. Sachse, `Model-based local density sharpening of cryo-EM maps <https://doi.org/10.7554/eLife.27131>`_, eLife 6: e27131 (2017).
* A. Bharadwaj and A.J. Jakobi, `Electron scattering properties and their use in cryo-EM map sharpening <https://doi.org/10.1039/D2FD00078D>`_, Faraday Discussions D2FD00078D (2022)
