.. gautomatch:

GAUTOMATCH
----------

**VERSIONS:**

* 0.56

**GENERAL INFORMATION**

Command-line based **GPU** program for the cross-correlation based particle picking in electron micrographs developed by Kai Zhang at LMB MRC.

**USAGE SPECIFIC INFORMATION**


.. code-block:: console

   module add gautomatch

   gautomatch   Micrographs/mic_*.mrc --apixM 1.34 --diameter 400 --min_dist 240 --T templates_lp40_3.2A.mrcs --write_pref_mic --lsigma_cutoff 1.2 --cc_cutoff 0.18 --lave_D 80 --lave_min -0.8 --lave_max 1.2  --exclusive_picking --excluded_suffix _rubbish.star --mask_excluded --write_ccmax_mic --write_pf_mic --write_pref_mic --write_bg_mic --write_bgfree_mic --write_lsigma_mic --write_mic_mask --extract_raw --do_pre_filter 1 --pre_lp 10  --pre_hp 1000 --lp 40 --boxsize 432


**DEVELOPER TUTORIAL/HELP PAGES**

* manual_

.. _manual: https://lab.rockefeller.edu/chen/assets/file/Gautomatch_Brief_Manual.pdf
