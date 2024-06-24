# Module 4 - When should I use a cluster?

## Long-running processes
Processes that exceed a typical runtime, often more than 24 hours, can be defined long-running processes, for example:
- Engineering: tasks such as aerodynamics, structural engineering, and fluid dynamics design and optimization.
- Financial sector: risk simulations and financial modeling to predict market trends or assess risks.
- Healthcare: molecular modeling for drug discovery and interaction simulations.

To deal with the long-running processes, checkpointing is usually used at fixed time interval to save progress and prevent data loss, and scheduling tools are needed to organize the job.

## GPU-accelerated workloads
When considering the use of an HPC cluster for GPU-accelerated workloads, it’s important to evaluate the availability and configuration of GPU resources, like the type and number of GPUs. Then, these GPUs are often set up with MIG (multi-instance GPU) to optimize for varied workloads, allowing multiple users or jobs to utilize the GPU resources efficiently. Furthermore, for jobs requiring multiple full GPUs, special requests should be made to the HPC administrators for reconfiguration.

### [Multi-instance GPU](https://docs.alliancecan.ca/wiki/MPI)

The Message Passing Interface (MPI) is a standard that describes a set of subroutines, functions, and objects for writing parallel programs in a distributed memory environment. As an open and non-proprietary standard, MPI programs can be easily ported to various computer systems. Applications using MPI can run on a large number of cores simultaneously, often achieving good parallel efficiency. Since memory is local to each process, some debugging aspects are simplified—one process cannot interfere with another's memory, and segmentation faults generate core files that can be processed with standard serial debugging tools.

However, managing communication and synchronization explicitly in MPI programs can make them appear more complex compared to those written with tools supporting implicit communication. Designing an MPI program requires careful consideration to minimize communication overhead and achieve good speed-up from parallel computation.

Parallel programs written using MPI follow an execution model called Single Program, Multiple Data (SPMD). The SPMD model involves running multiple copies of a single program, with each copy (or "process") assigned a unique rank. Each process can obtain its rank when it runs. When different behavior is needed for different processes, an "if" statement based on the process's rank is used to execute the appropriate instructions.

![SPMD model illustrating conditional branching to control divergent behaviour](https://docs.alliancecan.ca/mediawiki/images/8/8a/SPMD_model.png) *SPMD model illustrating conditional branching to control divergent behaviour*

## Many asynchronous parallel processes
Asynchronous parallel processes are processes that can run independently and do not need to communicate with each other during execution, for example:
- Hyperparameter sweeps: running multiple independent experiments to optimize parameters.
- Simulations with random seeds: running many instances of a simulation with different initial conditions.

## Many synchronously parallel processes
Synchronously parallel processes are suitable for large simulations that span multiple nodes or training very large models across multiple GPUs or nodes, and these jobs typically rely on MPI (Message Passing Interface) or similar software for data transfer between nodes.

## When not to use a cluster
However, we should not expect that any program will automatically run faster on a cluster. In fact a serial program that does not need much memory may run slower on an HPC cluster than on a newer laptop or desktop computer for some reasons:
- CPU Clock Speed: HPC clusters often prioritize parallel processing capabilities over individual core speed. A modern laptop or desktop might have a higher clock speed for single-core performance, making it faster for serial tasks.
- Resource Allocation: HPC clusters typically manage resources to optimize the performance of large parallel jobs. This can include scheduling policies and job queuing systems that might add overhead or delay the execution of smaller, single-threaded programs.
- I/O Bottlenecks: HPC clusters often have shared file systems, which can become bottlenecks, especially if many users or jobs are accessing the storage simultaneously. In contrast, a laptop or desktop with a dedicated SSD might provide faster I/O performance for the program.
- Interconnect Overhead: HPC clusters are designed to optimize communication between nodes for parallel processing. Running a serial program on such a system might introduce unnecessary overhead from network interconnects and communication protocols, even if they are not needed by the serial program.
