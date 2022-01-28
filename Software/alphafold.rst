.. alphafold:

ALPHAFOLD
---------

**VERSIONS:**

* 2.0

**GENERAL INFORMATION**

*AlphaFold ia an AI system developed by DeepMind that predicts a protein's 3D structure from its amino acid sequence. It regularly achieves accuracy competitive with experiment.*

**USAGE SPECIFIC INFORMATION**

* loading from the modules

.. code-block:: console

   module add alphafold

* we have an in-house written python script ``runAlphafold.py`` to streamline the configuration of the job which requires only the file with a sequence

.. code-block:: console

   runAlphafold.py --f <sequence.fasta>

* run the script without any input to get the list of all parameters

**DEVELOPER TUTORIAL/HELP PAGES**

* methodology_

.. _methodology: https://www.nature.com/articles/s41586-021-03819-2
