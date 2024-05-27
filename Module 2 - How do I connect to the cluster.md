# Module 2 - How do I connect to the cluster?

To access the resources of an HPC cluster you need to connect to it through your computer. In this module you will learn how to connect to a cluster, navigate its file system, and run code on the cluster. You will also learn how to transfer data to and from the cluster.


# Learning Outcomes

By the end of this module, you will be able to:

- Connect to an HPC cluster using SSH
- Edit code and run a simple job on the cluster
- Use a variety of tools to transfer data to and from the cluster


# Connecting to the Cluster using SSH

<!-- - What is SSH?
- How to connect to the cluster using SSH?
- How to set up SSH keys? -->

## What is SSH?

SSH or Secure Shell is a network protocol and a software that lets you control a computer remotely over the internet. It uses encryption to establish a secure connection between your local machine and a remote server, like an HPC cluster. You can access the cluster through your computer's command line using SSH to run jobs and transfer files to and from the cluster.


## How to connect to the cluster using SSH?

To connect to the cluster using SSH, you need a local machine (your laptop) with an SSH client software installed and internet access. Most operating systems come pre-installed with an SSH client. You can check if your computer has an SSH client by running the following command in your terminal:

```bash
ssh -V
```

If you see the version information of the SSH client, you have it installed and are ready to connect to the cluster. Next, you need the address or hostname of the cluster. The hostname tells the SSH client where to find the cluster. You also need a username on the cluster to log in. Once you have the hostname and username, you can connect to the cluster using the following command:

```bash
ssh usename@hostname
```

For example, to connect to the cluster with the hostname `supercomputer.awesome.ca` and the username `andy`, you would run,

```bash
ssh andy@supercomputer.awesome.ca
```

When you run this command, you are essentially trying to log in to the cluster over the internet. This means that unless the cluster has terrible security, you will need a password to log in. In some cases you will be prompted for a password. In some cases a two-factor authentication will be required where you enter a one-time password or accept a request sent to your phone or email.

After you have successfully logged in, you will be greeted with a new command prompt and perhaps some information about the cluster indicating that you are now connected to the cluster. This prompt may look like the following,

```bash
[andy@supercomputer ~]$
```

At this point you are connected to the cluster and can run commands as if you were sitting in front of that computer. You can navigate the file system, make and edit files, and run software on the cluster. (We will cover these topics in the up-coming sections.)


## How to set up SSH keys?

<!-- Motivate the need for SSH keys. Explain how to set up SSH keys. -->


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
