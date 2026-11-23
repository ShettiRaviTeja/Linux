# Types of Kernel
### Monolithic Kernel
- A Monolithic Kernal manages almost all major operating system services inside a single kernal space.
- These services include:
  - Process Management
  - Memory Management
  - Device Drivers
  - File System Management
- All these components work together within the kernal.
- It provides high performance but a problem in one kernel component can affect the entire system.
- Example: Linux.

### Microkernel
- A Microkernel keeps only the essential operating system services inside the kernal. Other services run separately in user space.
- For example:
  - Essential Services: Basic memory management and process scheduling.
  - Other Services: Device drivers and file system services.
- Communication happens through inter-process communication (IPC).
- Example: MINIX 3, QNX.

### Exokernel
- An Exokernel allows applications to have more direct control over hardware resources.
- Applications using an exokernel have greater control over hardware resources, but developers must handle more complexity.
- It provides minimal abstraction and allows applications to manage hardware resources directly through secure resource allocation and protection mechanisms.

### Hybrid Kernel
- A Hybrid Kernel combines features of both Monolithic and Microkernel architectures.
- It tries to provide:
  - High performance
  - Better modularity
  - Flexibility
  - Stability
- Some operating system services run in kernel space, while the architecture also uses modular design principles.
- This provides a balance between direct communication and separation of responsibilities.
- Example: Windows NT kernel and macOS XNU kernel.
- Example: MIT Exokernel.
