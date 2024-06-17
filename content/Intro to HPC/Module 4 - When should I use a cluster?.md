# Module 4 - When should I use a cluster?

## Long-running processes
Processes that exceed a typical runtime, often more than 24 hours, can be defined long-running processes, for example:
- Engineering: tasks such as aerodynamics, structural engineering, and fluid dynamics design and optimization.
- Financial sector: risk simulations and financial modeling to predict market trends or assess risks.
- Healthcare: molecular modeling for drug discovery and interaction simulations.

To deal with the long-running processes, checkpointing is usually used at fixed time interval to save progress and prevent data loss, and scheduling tools are needed to organize the job.

## GPU-accelerated workloads
When considering the use of an HPC cluster for GPU-accelerated workloads, it’s important to evaluate the availability and configuration of GPU resources, like the type and number of GPUs. Then, these GPUs are often set up with MIG (multi-instance GPU) to optimize for varied workloads, allowing multiple users or jobs to utilize the GPU resources efficiently. Furthermore, for jobs requiring multiple full GPUs, special requests should be made to the HPC administrators for reconfiguration.

## Many asynchronous parallel processes
Asynchronous parallel processes are processes that can run independently and do not need to communicate with each other during execution, for example:
- Hyperparameter sweeps: running multiple independent experiments to optimize parameters.
- Simulations with random seeds: running many instances of a simulation with different initial conditions.

## Many synchronously parallel processes
Synchronously parallel processes are suitable for large simulations that span multiple nodes or training very large models across multiple GPUs or nodes, and these jobs typically rely on MPI (Message Passing Interface) or similar software for data transfer between nodes.

## When not to use a cluster
However, we should not expect that any program will automatically run faster on a cluster. In fact a serial program that does not need much memory may run slower on an HPC cluster than on a newer laptop or desktop computer. Besides, when jobs are very high in I/O (input/output) operations, it can lead to bottlenecks and is not suitable to use a cluster.
