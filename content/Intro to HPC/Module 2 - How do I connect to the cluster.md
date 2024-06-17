# Module 2 - How do I connect to the cluster?

To access the resources of an HPC cluster you need to connect to it through your computer. In this module you will learn how to connect to a cluster, navigate its file system, and run code on the cluster. You will also learn how to transfer data to and from the cluster.


# Learning Outcomes

By the end of this module, you will be able to:

- Connect to an HPC cluster using SSH
- Edit code and run a simple job on the cluster
- Use a variety of tools to transfer data to and from the cluster


# Connecting to the Cluster using SSH

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

Your connection to the cluster through SSH is secured by a password. This means you need to enter your password every time you connect to the cluster. This can quickly become cumbersome and somewhat redundent if you are using the same client computer (e.g. your personal laptop). An alternative is to set-up a public key encyption instead of a password allowing you to connect to the cluster without entering your password every time you want to connect.

Here we show the procedure for generate SSH keys in linux. You can use the `ssh-keygen` software by typing the following command,

```bash
ssh-keygen -b 4096 -t rsa
```

After entering this command you will be prompted to enter filename and passphrase for your SSH keys (you can choose to have no passphrase). After generating the SSH keys you will have two new files in the path selected during generation: a public key with `.pub` extension and a private key for you to keep safe.

To transfer your public key to a cluster you can use the `ssh-copy-id` command,

```bash
ssh-copy-id -i ~/.ssh/key.pub supercomputer.awesome.ca
```

Alternatively, you can set-up this public key using the Digital Research Alliance of Canada's website. If this is the first time you are using this website, you first need to register for a new account. To register, you must ask your supervisor to provide you with a special code you can enter when registering. After your registration you can log-in and navigate the menues to find the SSH key tab allowing you to paste your public key manually in the website.

Now you can connect to the cluster without entering your password with the following comamnd,

```bash
ssh -i ~/.ssh/key usename@hostname
```

To avoid typing the path to your private key or the full `username@hostname` each time you want to connect to the cluster, you can set-up the following configuarions in your ssh config file (`~/.ssh/config`),

```
Host awesome
  HostName hostname
  IdentityFile path/to/private/key
  User username
  ForwardAgent yes
```

Let's go through this config line by line.

- In the first line you set-up an alias for this particular connection. From now on you can connect to the cluster by typing `ssh awesome` in the command line.
- In the second line you have to enter the cluster's hostname.
- In the third line you enter the path to the SSH private key you generated in the previous step.
- In the fourth line you enter your username on the cluster.
- The last line let's you access your private key while on the cluster. This allows you to access other services (like Github) that require SSH keys.


Now you are ready to connect to the cluster via a single command,

```bash
ssh awesome
```

## Multi-factor authentication

Like most other web-based services today, your connection to the cluster is secured through another layer of protction via multi-factor authentication. This usually means that you have to press a button on your phone each time you want to establish connection to the cluster. While this is a nice way to protect your information on the cluster, it can quickly become annoying when you are connecting to the cluster several times during a single work session. To prevent this issue we can reduce the number of times the server asks you to use the multi-factor authenticator by setting up a few more lines of SSH configuation.


```
Host awesome
  HostName hostname
  IdentityFile path/to/private/key
  User username
  ForwardAgent yes
  ControlMaster auto
  ControlPath ~/.cache/ssh/%r@%h:%p
  ControlPersist yes
```

The new lines will keep your computer connected to the cluster after the first connection is established. This means while you work on the same computer on the same network without turning your computer off you can reconnect to the cluster without using the multi-factor authenticator.



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
