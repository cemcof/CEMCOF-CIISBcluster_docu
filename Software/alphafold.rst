.. alphafold:

ALPHAFOLD
---------

**VERSIONS:**

* 2.1.1 (archived)
* 2.1.2 (archived)
* 2.2.0
* 2.2.4

**GENERAL INFORMATION**

*AlphaFold is an AI system developed by DeepMind that predicts a protein's 3D structure from its amino acid sequence. It regularly achieves accuracy competitive with experiment.*

**USAGE SPECIFIC INFORMATION**

* loading from the modules

.. code-block:: console

   module add alphafold

* module is provided with a bash wrapper to streamline the configuration of the job which requires only the file with a sequence

.. code-block:: console

   alphafold -f <sequence.fasta>

* run the script without any input or ``-h`` option to get the list of all parameters
* for optimal performance, the job should be submitted to nodes containing local copy of the Alphafold Database (option ``alphafold=True``). Otherwise, remote database is used and performance is affected. User is informed about the selected database in the output file. Example of ``qsub`` command:

.. code-block:: console

   qsub -q default -l select=1:ncpus=8:ngpus=1:mem=50gb:scratch_local=50gb:alphafold=True -l walltime=24:00:00 run_af

* path to the Alphafold database can be overridden by specifying ``data_dir`` variable.

.. code-block:: console

   export data_dir="/user/path/to/a/database"
   alphafold -f <sequence.fasta>

**DEVELOPER TUTORIAL/HELP PAGES**

* methodology_

.. _methodology: https://www.nature.com/articles/s41586-021-03819-2
