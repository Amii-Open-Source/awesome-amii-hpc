# Module 1 - What is a cluster?
## Infrastructure of an HPC cluster
An HPC cluster is a collection of separate servers (computers), called nodes, which are connected via a fast interconnect. All cluster nodes have the same components as a laptop or desktop: CPU cores, memory and disk space. The difference between personal computer and a cluster node is in quantity, quality and power of the components.

An HPC cluster basically contains a head node (or called login node), where users log in; compute nodes, where majority of computations is run, and on these nodes, computations can be run both on CPU cores and on GPUs; a storage server, which contains a collection of storage nodes connected with each other and provide access to data stored on the cluster.
![An HPC cluster topology](https://www.hpc.iastate.edu/sites/default/files/uploads/HPCHowTo/HPCCluster.JPG)
         
## Networking of an HPC cluster
![Topology of "Hortense" Tier-1 supercomputer, hosted by Ghent University](https://static.wixstatic.com/media/5446c2_a7e080a424d242eb8334cd98be1899bd~mv2.png/v1/fill/w_1729,h_1357,al_c,q_95,enc_auto/07072023_VSC-Tier-1-Hortense_Illustration.png)

## Login nodes
The login nodes of clusters are the portal to the outside world. Users connect to these nodes mostly using SSH (Secure Shell), which is a common method for secure remote login from one computer to another. Other ways like connecting via remote desktop and HPC JupyterHub are also provided in some HPC clusters. When connecting to the cluster, you initially interact with these login nodes. The nodes handle many concurrent users, typically between 50 and 100. It's crucial that these nodes are quick and responsive to ensure that users do not spend excessive time waiting for simple commands to execute. 
## Compute nodes
Compute notes are the processing component of an HPC cluster. They execute the workload using local resources, like CPU, GPU, FPGA and other processing units. These workloads also use other resources on the compute node for processing, such as the memory, storage and network adapter. 
### GPUs
Data of HPC cluster Examples:
- NVIDIA DGX A100 Systems: Each DGX A100 system is powered by eight NVIDIA A100 GPUs that are configured in a hybrid cube-mesh topology that uses NVIDIA NVLink® and NVSwitch® technology.
- "Hortense" Tier-1 supercomputer, hosted by Ghent University: The phase one GPU partition consists 20 workernodes, each with 2x 24-core AMD Epyc 7402 CPU 2.8 GHz (48 cores per node) and 4x NVIDIA A100-SXM4 (40 GB GPU memory), NVLink3. The phase two GPU partition is almost the same except the larger GPU memory.
- FRONTIER, ORNL(Oak Ridge National Laboratory)’s exascale supercomputer: 4 Purpose Built AMD Instinct 250X GPUs.
- Aurora: The GPU architecture includes 6 Intel Data Center GPU Max Series; Tile-based chiplets, HBM stack, Foveros 3D integration, 7nm
### CPUs and RAM 
Data of HPC cluster Examples:
- "Hortense" Tier-1 supercomputer: Phase 1 main CPU partition consists 342 workernodes, each with 2x 64-core AMD Epyc 7H12 CPU 2.6 GHz (“Rome” microarchitecture, 128 cores per node) and 256 GiB RAM (~2GB/core).
- FRONTIER: the maximum achieved performance 1,194.00 PFlop/s in the real world condition.
- AURORA by Intel: the peak performance 1,059.33 PFlop/s in the real world condition.
## A storage server
A server dedicated to storing and managing large amounts of data across many hard drives. 
### Storage server and configuration
The NetAPP AFF A800 system by NVIDIA supports a maximum capacity of 9.6 petabytes, which equates to around 320 solid-state drives (SSDs) each with a capacity of 30 TB. Regarding the configuration, it uses FlexGroup volume, a logical storage provisioning method that creates a single pool of storage distributed across multiple nodes in the storage cluster, enhancing both capacity and performance.
### Communicate to Compute/Infra Nodes Over the Network
High-speed networking technologies, such as InfiniBand or Ethernet, are employed. Various file systems and access protocols are supported, including NFS for traditional sharing, and more specialized systems like Lustre for distributed environments.
### File systems
Lustre File System, known for its high performance in large-scale, complex computing environments; manages data distribution and access efficiently across multiple storage nodes. Other options like GPFS™ (IBM Spectrum Scale) and other systems might be considered based on specific needs and operational contexts.
### Tiered Storage
In the European model for HPC, a distinction is made between three levels:
1.	Tier-2: the computing capacity that is available at research institutions.
2.	Tier-1: the computing capacity that exceeds the capacity of an institution in terms of needs and costs and which is provided at the level of a region or country.
3.	Tier-0: the very large-scale computing infrastructure.

while Tier-3 includes single computers.
![Vlaams supercomputer centrum](https://static.wixstatic.com/media/5446c2_002fa8b33249455b80a94926fc81cc26~mv2.jpg/v1/crop/x_0,y_118,w_1015,h_482/fill/w_1015,h_482,al_c,q_85,enc_auto/07032022_Tiering-Model.jpg)
## A backup storage server
The server is located off-site. Backup Strategies on Tier-1 data platform of Vlaams supercomputer centrum include differential Backups which performed daily, which capture only the changes made since the last full backup, rather than copying all files anew, and complete backups, which conducted monthly, these involve copying all data as it exists at that time, ensuring that a complete snapshot of data is available for recovery.
