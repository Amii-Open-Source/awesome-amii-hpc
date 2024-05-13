# Module 2 - How do I connect to the cluster?

To access the resources of an HPC cluster you need to connect to it through your computer. In this module you will learn how to connect to a cluster, navigate its file system, and run code on the cluster. You will also learn how to transfer data to and from the cluster.


# Learning Outcomes

By the end of this module, you will be able to:

- Connect to an HPC cluster using SSH
- Edit code and run a simple job on the cluster
- Use a variety of tools to transfer data to and from the cluster


# Connecting to the Cluster using SSH

- What is SSH?
- How to connect to the cluster using SSH?
- How to set up SSH keys?


# Running Code on the Cluster

- VSCode remote development (edit code directly on the cluster)
- Running code on the login-node (why is this bad? when is it okay?)
- Interactive jobs (commands to request and connect to an interactive job)
- Submitting jobs to the scheduler (commands to submit a job)


# Transferring Data to and from the Cluster

- Tools for transferring data (why do we need multiple tools?)
- scp
    - Transferring a small number of small files (wrapper around SSH)
- rsync
    - Transferring a large number of files (benefits of compression and restarting)
- Globus
    - Transferring very large data (how large?)
    - Transferring data between clusters (Canarie network)
- git
    - Transferring and syncing code
    - How to clone a github repository on the cluster (setting up ssh keys?)


## Activity: Running a Simple Job on the Cluster

In this activity, you will connect to the cluster via SSH and submit a very simple Python job script.
