.. _alphafold:

ALPHAFOLD
---------

**VERSIONS:**

* 2.1.1
* 2.1.2
* 2.2.0

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
* submit the job to the nodes ciisb1, or ciisb14 for optimal performance, because they contain a local copy of the Alphafold Database. Otherwise, remote database is used and performance is affected. User is informed about the selected database in the output file. Example of ``qsub`` command:

.. code-block:: console

   qsub -q default -l select=1:ncpus=1:ngpus=1:mem=50gb:scratch_local=50gb:alphafold=True -l walltime=24:00:00 run_af

**DEVELOPER TUTORIAL/HELP PAGES**

* methodology_

.. _methodology: https://www.nature.com/articles/s41586-021-03819-2
