# Module 3 - What can I do on the login nodes?

When you first connect to an HPC cluster, you will be placed on a login node. Unlike your personal computer, login nodes are not meant for running resource-intensive programs. In this module, you will learn about the most important things you can do on the login node, including submitting jobs to the scheduler and handling software and data.

# Learning Outcomes

By the end of this module, you will be able to:

- Describe typical workflows and limitations on login nodes
- Submit jobs to SLURM
- Compile code, install libraries, and access software on the login nodes


# Login Nodes

- What are login nodes?
- What you should not be doing on login nodes
    - Amii and DRAC’s policies for running programs on login nodes
    - DRAC documentation for login node policies for various clusters (cedar, niagara, beluga, etc)
- What are the typical workflows on login nodes?


# Scheduling Jobs

- What is SLURM?
    - SLURM documentation + DRAC documentation for scheduling jobs
- How to submit a job to SLURM
- What is a job script?


# Handling Data and Software

- Accessing software
    - The “module” command (“module avail” and “module load”)
- Installing precompiled libraries
    - Why should you use precompiled libraries
- Compiling code (should I be doing this on the login node?)
    - Though you shouldn’t use more than X cpus or Y memory to compile code. To do more, schedule it as a job.
