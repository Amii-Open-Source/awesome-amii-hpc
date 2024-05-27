# Awesome Amii HPC [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

[![Contributions](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](./CONTRIBUTING.md)

---

## Table of Contents

1. [What is a cluster?](#what-is-a-cluster)
2. [How do I connect to the cluster?](#how-do-i-connect-to-the-cluster)

## What is a cluster?

* [Wikipedia](https://en.wikipedia.org/wiki/High-performance_computing) - An introduction of HPC.
* [Nvidia: MIG user guide documentation](https://docs.nvidia.com/datacenter/tesla/mig-user-guide/index.html#abstract) - A user guide documentation of multi-instance GPU from Nvidia.
* [Ubuntu HPC](https://www.youtube.com/watch?v=tGIobcyKViI&t=2s) - A Youtube video introducting cluster components.
* [Top 500 list](https://www.top500.org/) - The data of top 500 listed supercomputers, which gives a scope of how fast and how much compute nodes are, and also introduction and comparison among these computers.
* [Iowa State University HPC Guides](https://www.hpc.iastate.edu/guides/introduction-to-hpc-clusters) - A collection of introductory guides for HPC including SLURM, globus, unix, python, julia, and much more.
* [An HPC User Guide](https://servicedesk.aub.edu.lb/TDClient/1398/Portal/KB/ArticleDet?ID=66391) - A collection of introductory guides for HPC including connection nodes, SLURM, job examples and applications.
### Compute Canada
* [Compute Canada: an introduction to HPC](https://training.incf.org/lesson/high-performance-computing-compute-canada) - A Youtube video introducting high-performance computing with the Compute Canada network, first providing an overview of use cases for HPC and then a hands-on tutorial.
* [Compute Canada: Cedar](https://docs.alliancecan.ca/wiki/Cedar) - An introduction of Cedar, a heterogeneous cluster located at Simon Fraser University.
* [Compute Canada: Graham](https://docs.alliancecan.ca/wiki/Graham) - An introduction of Graham, a heterogeneous cluster located at the University of Waterloo.
* [Compute Canada: Narval](https://docs.alliancecan.ca/wiki/Narval/en) - An introduction of Narval, a general purpose cluster located at the École de technologie supérieure in Montreal.
* [Compute Canada: Béluga](https://docs.alliancecan.ca/wiki/B%C3%A9luga/en) - An introduction of Béluga, a general purpose cluster situated at the École de technologie supérieure in Montreal.
* [Compute Canada: Niagara](https://docs.alliancecan.ca/wiki/Niagara) - An introduction of Niagara, a homogeneous cluster owned by the University of Toronto and operated by SciNet.
* [Compute Canada: Systems available](https://docs.alliancecan.ca/wiki/Getting_started#What_systems_are_available?) - A brief introduction for the five systems of Compute Canada and the clusters' types.
* [Compute Canada: Allocations and compute scheduling](https://docs.alliancecan.ca/wiki/Allocations_and_compute_scheduling#Choosing_GPU_models_for_your_project) - A brief tutorial of choosing GPU models for your project.

## How do I connect to the cluster?

* [SSH quickstart](https://linuxhandbook.com/ssh-basics/) - Step-by-step ssh and scp guide.
* [Compute Canada: SSH](https://docs.alliancecan.ca/wiki/SSH) - An introduction of Secure Shell used to connect to remote machines securely.
* [Compute Canada: Transferring data](https://docs.alliancecan.ca/wiki/Transferring_data) - Overview of options for transferring data to and between clusters (Glubus, rsync, scp, etc.).
* [Compute Canada: Globus](https://docs.alliancecan.ca/wiki/Globus) - Setup and tutorial for Globus with Compute Canada.
* [Globus docs](https://docs.globus.org) - Globus tutorials and documentations.
* [Globus video tutorial](https://www.youtube.com/watch?v=-j7Mp3FN1zo) - Youtube video introduction to Globus for researchers and new users.
* [VS Code remote development](https://code.visualstudio.com/docs/remote/remote-overview) - Visual studio code remote development guide.
* [Rsync quickstart](https://linuxize.com/post/how-to-use-rsync-for-local-and-remote-data-transfer-and-synchronization/) - Step-by-step rsync guide.
* [Compute Canada: Interactive jobs](https://docs.alliancecan.ca/wiki/Running_jobs#Interactive_jobs) - Compute Canada documentation for running interactive jobs.
* [Github SSH authentication](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) - Connecting Github account to your computer and the cluster.
* [git - the simple guide](https://rogerdudler.github.io/git-guide/) - A short introduction and Step-by-step git guide. 
* [Compute Canada: Storage and file management](https://docs.alliancecan.ca/wiki/Storage_and_file_management) - An introduction of a wide range of storage options to cover the needs of very diverse users of Compute Canada.

## When should I use a cluster?



# synchronous parallelism
* [Tensorflow: Distributed training](https://www.tensorflow.org/guide/keras/distributed_training) - Introduction and tutorial of Multi-GPU and distributed training.
* [Wikipedia: GNU parallel](https://en.wikipedia.org/wiki/GNU_parallel) - Introduction and user's guide of GNU parallel.
* [Compute Canada: GNU parallel](https://docs.alliancecan.ca/wiki/GNU_Parallel) - An introductory tutorial of using GNU parallel.
* [GNU parallel tutorial documentation](https://www.gnu.org/software/parallel/parallel_tutorial.html) - A tutorial of GNU parallel, including its functionality, options and syntax.
## openMPI
* [Open-MPI documentation](https://www.open-mpi.org/doc/) - A series of versions for Open MPI documentations.
* [Open MPI v5.0.x](https://docs.open-mpi.org/en/v5.0.x/) - The documentation of current release Open MPI.
* [SLURM: MPI users guide](https://slurm.schedmd.com/mpi_guide.html) - An introductory tutorial of various MPI implementations.
* [Github: Open-MPI tutorial](https://usc-rc.github.io/tutorials/open-mpi) - A tutorial of using Open MPI.
* [Compute Canada: MPI-IO](https://docs.alliancecan.ca/wiki/MPI-IO) - Description and using tutorial of MPI-IO.

# jax
* [jax.pmap](https://jax.readthedocs.io/en/latest/_autosummary/jax.pmap.html) - Step-by-step jax.pmap guide.
* [Compute Canada: Flax](https://docs.alliancecan.ca/wiki/Flax) - Introduction and tutorial of Flax, a neural network library and ecosystem for JAX that is designed for flexibility, including the guidance of using jax.pmap.

# Slurm 
## Module 4 - Preemption and checkpointing
* [Compute Canada: Checkpoints](https://docs.alliancecan.ca/wiki/Points_de_contr%C3%B4le/en) - A tutorial of creating and loading a checkpoint.
* [Compute Canada: Machine Learning tutorial](https://docs.alliancecan.ca/wiki/Tutoriel_Apprentissage_machine/en#Checkpointing_a_long-running_job) - A toturial of checkpointing a long-running job.
* [Tensorflow: Checkpoint guide](https://www.tensorflow.org/guide/checkpoint) - Guidance for training checkpoints while using Tensorflow.

# Managing research data 
## HPC Storage Systems
* [Compute Canada: Lustre](https://docs.alliancecan.ca/wiki/Tuning_Lustre) - An introduction and tutorial of Lustre Filesystem.