.. mmseqs2:

MMseqs2
---------

**VERSIONS:**

* 13-45111

**GENERAL INFORMATION**

MMseqs2 (Many-against-Many sequence searching) is a software suite to search and cluster huge protein and nucleotide sequence sets. MMseqs2 is open source GPL-licensed software implemented in C++ for Linux, MacOS, and (as beta version, via cygwin) Windows. The software is designed to run on multiple cores and servers and exhibits very good scalability. MMseqs2 can run 10000 times faster than BLAST. At 100 times its speed it achieves almost the same sensitivity. It can perform profile searches with the same sensitivity as PSI-BLAST at over 400 times its speed.

**USAGE SPECIFIC INFORMATION**

* loading from the modules

.. code-block:: console

   $ ssh ciisb.ceitec.muni.cz
   $ module add mmseqs2
   $ mmseqs # prints help
   $ source $MMSEQS_HOME/util/bash-completion.sh # For bash completion feature

**DEVELOPER TUTORIAL/HELP PAGES**

* `Documentation <https://github.com/soedinglab/mmseqs2/wiki>`_
* `Github <https://github.com/soedinglab/MMseqs2>`_

**REFERENCES**

* Steinegger M and Soeding J. MMseqs2 enables sensitive protein sequence searching for the analysis of massive data sets. Nature Biotechnology, `doi: 10.1038/nbt.3988 (2017) <https://www.nature.com/articles/nbt.3988>`_.
* Steinegger M and Soeding J. Clustering huge protein sequence sets in linear time. Nature Communications, `doi: 10.1038/s41467-018-04964-5 <https://www.nature.com/articles/s41467-018-04964-5>`_ (2018).
* Mirdita M, Steinegger M and Soeding J. MMseqs2 desktop and local web server app for fast, interactive sequence searches. Bioinformatics, `doi: 10.1093/bioinformatics/bty1057 <https://academic.oup.com/bioinformatics/article/35/16/2856/5280135>`_ (2019).
* Mirdita M, Steinegger M, Breitwieser F, Soding J, Levy Karin E: Fast and sensitive taxonomic assignment to metagenomic contigs. Bioinformatics, `doi: 10.1093/bioinformatics/btab184 <https://doi.org/10.1093/bioinformatics/btab184>` (2021).
