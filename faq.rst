Frequently Asked Questions
==========================

How do I cite use of this HPC resource?
---------------------------------------

Citations and acknowledgements help us demonstrate the importance of computational resources and support staff in research at our institutes, and we ask that you acknowledge use of this system in any publications, presentations, or talks that were made possible because of it. An acceptable example citation is below:

    *The authors acknowledge the Research/Scientific Computing teams at The James Hutton Institute and NIAB for providing computational resources and technical support for the "UK's Crop Diversity Bioinformatics HPC" (BBSRC grant BB/S019669/1), use of which has contributed to the results reported within this paper.*

If you cite or acknowledge us in your work, please :doc:`contact-us` to let us know.


What hardware is available on the cluster?
------------------------------------------

The cluster has 55 physical nodes, providing a total of 1,764 Intel Xeon compute cores (3,528 threads) and 15,296 GB of memory. A 1.5 PB parallel storage array is complemented by a further petabyte of backup capacity. A full description is provided on the :doc:`system-overview` page.


How do I get an account on the system?
--------------------------------------

Please visit :doc:`user-accounts` for details.


How do I connect to the cluster?
--------------------------------

The cluster’s head node (where you can submit jobs from) is called ``gruffalo``, and you'll need an SSH client to connect. One is built into Linux and macOS, but for Windows you may need to install a separate client (WSL, Cygwin, MobaXterm and PuTTY are all good choices).

You connect via SSH using::

  $ ssh <username>@gruffalo.cropdiversity.ac.uk

making sure to replace ``<username>`` with the username you were allocated when requesting an account. More detailed connection instructions are available on the :doc:`ssh` page.
 

I've forgotten my password - can you recover it?
------------------------------------------------

Please :doc:`contact-us` for help with passwords. We can't recover (or even see) your password, but we can reset it in order to allow you to log in again, at which point you'll be prompted to set a new password.


Can I run jobs directly on gruffalo?
------------------------------------

Eeep! Don’t do that, no.

You can use ``gruffalo`` for compiling and debugging code, installing software, editing and managing files, submitting jobs, or any other work that is not long-running or computationally intensive, but for everything else, you must submit a job using Slurm (see :doc:`slurm-overview`).


How do I submit jobs to the cluster?
------------------------------------

The cluster uses the Slurm Work Manager job scheduling system and all jobs should be submitted (from ``gruffalo``) to Slurm, where they will be allocated resources on one of the underlying compute nodes. More detailed instructions can be found on the :doc:`slurm-overview` page.
  
What software is available?
---------------------------

In general, there is very little application software installed system-wide (check ``/mnt/shared/apps`` for details), as most tools can be managed and maintained individually using tools like :doc:`bioconda` and :doc:`singularity`.

If you get stuck installing applications though, don't hesitate to :doc:`contact-us`.

How should I manage my data?
----------------------------

Considerate data management is everyone's responsibility, and it's critical that you ensure you're only storing (and backing up) important project-related data while keeping temporary and/or intermediate working data to a minimum. This helps keep the system running smoothly for everyone and ideally means we don't need to start enforcing quotas.

You can find more information on how we expect you to manage your data on the :doc:`data-storage` page. A summary of your current disk usage is shown on login, with detailed tracking available via :doc:`monitoring`.

Can I access the cluster when off site?
---------------------------------------

Yes. Access to the cluster via a username/password combination is available if you are connected via a :doc:`organizations` network address, but for other locations you must first enable your account for SSH public key authentication, described in more detail on the :doc:`remote-access` page.


Is training available to help me with Linux or using the cluster?
-----------------------------------------------------------------

This is something we're actively investigating.

In the meantime, there are some basic guides covering :doc:`linux-basics` and :doc:`tips`, as well as more in-depth information for getting the most out of cluster computing in the various topics listed under **High Performance Computing**.

It's also worth joining our Slack workspace (https://cropdiversity-hpc.slack.com) where there are plenty of expects on hand to help answer your questions.

Why does the login message show remaining space as a range?
-----------------------------------------------------------

The BeeGFS storage system uses transparent compression to automatically compress every file it stores. The free space message looks at the current compression ratio across system and uses that to estimate how much more data *could* be stored, if that same compression ratio were to apply. Obviously the final result will be different based on how compressible newly added files are, but it will be somewhere within the range shown.

Why "gruffalo"?
---------------

The name ``gruffalo`` goes way back to the early days of HPC at the Scottish Crop Research Institute (that merged with the Macaulay Land Use Institute to become the James Hutton Institute in 2011). Our first cluster - circa 2004 - used this name, and we've carried it on ever since, upgrading and/or rebuilding it across a range of hardware and software (RHEL, Fedora, CentOS) generations.
