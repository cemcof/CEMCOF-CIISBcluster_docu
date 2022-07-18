.. hhsuite:

HH-suite
---------

**VERSIONS:**

* 3.3.0

**GENERAL INFORMATION**

The HH-suite is an open-source software package for sensitive protein sequence searching based on the pairwise alignment of hidden Markov models (HMMs).

**USAGE SPECIFIC INFORMATION**

.. code-block:: console

   $ ssh ciisb.ceitec.muni.cz
   $ module add hhsuite
   
   $ hhblits -i <input-file> -o <result-file> -n 1 -d <database-basename> # single search iteration
   $ hhblits -i <input-file> -o <result-file> -oa3m <result-alignment> -d <database-basename> # alignment

**DEVELOPER TUTORIAL/HELP PAGES**

* `Documentation <https://github.com/soedinglab/hh-suite/wiki>`_
* `Github <https://github.com/soedinglab/hh-suite>`_

**REFERENCES**

* Steinegger M, Meier M, Mirdita M, Vöhringer H, Haunsberger S J, and Söding J (2019) HH-suite3 for fast remote homology detection and deep protein annotation, BMC Bioinformatics, 473. `doi: 10.1186/s12859-019-3019-7 <https://doi.org/10.1186/s12859-019-3019-7>`_
