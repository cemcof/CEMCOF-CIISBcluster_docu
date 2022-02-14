.. general_usage:

Usage
-----

Following the login to the frontend node
``ciisb.ceitec.muni.cz``,
the users shall setup the computational task, which is subsequently started on one of the computational nodes. It is prohibited to run any computational task on the frontend node. On the other hand, it is allowed to use the frontend for simple graphical tasks (*e.g. class selection in Relion*).

**SOFTWARE**

The installed software is accessible through the application *modules*. Use the commands:

.. code-block:: console

   module av                       # to list all available software packages
   module list                     # to list the software packages in the active path
   module load <software-name>     # to add particular software package to the active path
   module unload <software-name>   # to remove the particular software package from the active path

For more details on the proper usage of the module command, please refer to MetaCentrumWiki_ or other dedicated resources (e.g. here_).

**PBS**

The computational tasks are not started directly but submitted to the PBS queueing system instead. In short,the commands or scripts are not run directly but submitted to the queue using ``qsub`` command. The parameters of the ``qsub`` command which will allocate the requested resources can be either set in the command line

.. code-block:: console

   qsub -q default -l select=1:ncpus=1:ngpus=1:mem=8gb -l walltime=2:00:00 ./run.py

by which we allocate 1 CPU, 1 GPU, 8GB RAM for 2 hours in the queue named *default* to run the computational tasks defined in the script *run.py*. Alternatively, the resources can be allocated within a header of a bash script which we will name e.g. *run.pbs* (see below).

.. code-block:: console

   #!/bin/bash
   #PBS -N jobName
   #PBS -q default
   #PBS -l select=1:ncpus=16:ngpus=4:mem=128gb:scratch_local=500gb
   #PBS -l walltime=18:00:00

   module add <software-name>

   cd $PBS_O_WORKDIR

   ./run.py

   clean_scratch

The script is then submitted to the queue using:

.. code-block:: console

   qsub run.pbs

The queue named *default* is a general queue which should be used in all jobs run on this cluster. Other imprtant resource variable are *scratch_local* and *scratch_ssd* which will allocate space either on the standard rotational disc, or the SSD disc of the computational node. The other important variables which can be used in the scripts comprise ``$SCRATCHDIR`` which points to the local scratch on the computational node allocated by *scratch_local* or *scratch_ssd* and ``$PBS_O_WORKDIR`` which corresponds to the directory from which the *qsub* command was initiated.

When we need to optimize the computational job or interact with it, we can start an interactive session using ``qsub -I`` command:

.. code-block:: console

   qsub -I -q default -l select=1:ncpus=1:ngpus=1:mem=8gb -l walltime=8:00:00


Please rerefer to the following page_ for more comprehensive overview of the proper usage.

**PBS Interactive Jobs with GUI**

To run PBS jobs with interactive Graphical User Interface (GUI), the job must be submitted in a specif way. Job employs `Virtual Network Computing`_ (VNC), which is a system for sharing remote desktop with very low latency. VNC system consists from two counterparts: VNC server, which is run on the computational node/remote machine; and VNC viewer, which is used to connect to the VNC server from the front node or workstation. The connection is tunneled through ssh.

Procedure:

1.) Prepare the job script in a separate directory (``~/tigervnc-pbs`` in this tutorial):

.. code-block:: console

   #!/bin/bash
   
   module add tigervnc
   
   vncserver-pbs

2.) Submit the job into the batch system specifying required resources. Note: Despite the resulting VNC session will be interactive, option ``-I`` is not used when submitting the job.

.. code-block:: console

   user@ciisb:~/tigervnc-pbs$ qsub -l select=1:ncpus=1:mem=2gb -l walltime=2:00:00 run_server

3.) When the job starts, a file ``VNCSERVER_INFO`` appears in the job directory. Print the content of the file to find out information about the started VNC session, especially session VNCID, which is needed for the connection. Obtained ``VNCSERVER_INFO`` file should look like this:

.. code-block:: console

   user@ciisb:~/tigervnc-pbs$ cat VNCSERVER_INFO
   
   >>> TigerVNC server started succesfully!
       Date: Mon Feb  7 17:15:04 CET 2022
      JobID: 9131.crybox-pro.ceitec.muni.cz
       Node: ciisb1.ceitec.muni.cz
       Logs: ciisb1.ceitec.muni.cz:/home/user/.vnc/ciisb1.ceitec.muni.cz.2.startlog
             ciisb1.ceitec.muni.cz:/home/user/.vnc/ciisb1.ceitec.muni.cz:2.log

      VNCID: user@ciisb1.ceitec.muni.cz:2

4.) Connect to the VNC server. Note: ssh connection to ``ciisb.ceitec.muni.cz`` must be established with option ``-X`` for the vncviewer to function properly.

.. code-block:: console

   user@ciisb:~/tigervnc-pbs$ module add tigervnc
   user@ciisb:~/tigervnc-pbs$ vncviewer user@ciisb1.ceitec.muni.cz:2 # replace with VNCID of your session
   
To maximize the benefits of the VNC, you should connect to the VNC server from your local session. If your work station does not have the CIISB software modules mounted (``/cemcofsw`` folder), you can obtain vncviewer in the following way:

.. code-block:: console

   user@localmachine:~$ scp username@ciisb.ceitec.muni.cz:/cemcofsw/general/ciisb-vncviewer-linux64.tar .
   user@localmachine:~$ tar xvf ciisb-vncviewer-linux64.tar
   user@localmachine:~$ cd ciisb-vncviewer-linux64
   user@localmachine:~/ciisb-vncviewer-linux64$ export TIGERVNC_PATH=~/ciisb-vncviewer-linux64 # Change according to actual location of the vncviewer
   user@localmachine:~/ciisb-vncviewer-linux64$ ./vncviewer user@ciisb1.ceitec.muni.cz:2 # replace with VNCID of your session
   
If you wish to execute vncviewer without specifying the path, you have to include these two lines into your ``.bashrc`` file:

.. code-block:: console
   export TIGERVNC_PATH=~/ciisb-vncviewer-linux64 # Change according to the actual location of the vncviewer
   export PATH=~/ciisb-vncviewer-linux64:$PATH # Change according to the actual location of the vncviewer
   
Then, after opening new terminal, you should be able to use vncviewer as:

.. code-block:: console

   user@ciisb:~/tigervnc-pbs$ vncviewer user@ciisb1.ceitec.muni.cz:2 # replace with VNCID of your session

5.) Vncviewer window opens, left click on the icon of the terminal in the left upper corner and access your GUI applications from the command line. If the window is closed, the session is not terminated and can be accessed later (until the job is killed by walltime). To reconnect, just rerun the ``vncviewer`` command with given VNCID.

6.) There are several options to terminate the VNC session:

a) Click the very left icon in the opened vncview and then click ``Exit`` in the opened popup. Logout terminates the VNC session and PBS job is finnished. This is the preferred way of termination.

b) Use one of the following commands:

.. code-block:: console

   user@ciisb:~$ vncserver-pbs -k VNCID

If you are logged on the machine with the VNC server, you can also use:

.. code-block:: console

   user@ciisb2:~$ vncserver -k :display_ID
   
c) Kill the PBS job via ``qdel`` (be carrefull about killing another of your jobs or sessions).

.. code-block:: console

   user@ciisb:~$ qdel 9131 # replace with your Job ID

In all cases, the ``VNCSERVER_INFO`` file is updated to contain information about the way of server termination, i.e.,

for standard termination:

.. code-block:: console

   >>> TigerVNC server was terminated!
       Date: Tue Feb  8 11:22:31 CET 2022

for killing by PBS:

.. code-block:: console

   >>> TigerVNC server was KILLED by the batch system!
       Date: Mon Feb  7 17:52:50 CET 2022

Additional information about ``vncserver-pbs``, ``vncserver`` and ``vncviewer`` commands can be obtained with ``-h`` option.

*Please, make sure to terminate all your VNC session, when your work is finished, to avoid unwanted blocking of the resources. You can use command* ``vncserver-pbs --list`` *to show all running VNC sessions on the cluster*

.. _MetacentrumWiki: https://wiki.metacentrum.cz/wiki/Application_modules
.. _here: https://modules.readthedocs.io/en/latest/
.. _page: https://wiki.metacentrum.cz/wiki/About_scheduling_system
.. _`Virtual Network Computing`: https://en.wikipedia.org/wiki/Virtual_Network_Computing
