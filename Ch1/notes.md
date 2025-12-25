Syscalls are the alpha and omega of system programming. A system call is made by a user-space program to request a service or resource from the kernel.
User space and kernel space are isolated for security and stability. When a program needs a privileged operation, it performs a system call, which triggers a trap into the kernel. The kernel executes the requested service in kernel mode and then returns to user mode.

API (Application Programming Interface) — the source-level interface a library/OS exposes: functions, types, constants, headers, and documented behavior.

ABI (Application Binary Interface) — the binary-level contract that lets compiled code work together. It includes type sizes and alignment, byte order, calling conventions (how arguments/returns use registers/stack), register usage, symbol naming/linking rules, and binary/object format.

An inode (index node) is a fundamental data structure in Unix-like file systems (Linux, macOS) that stores metadata about files and directories, like permissions, ownership, size, timestamps, and pointers to the actual data blocks on disk, but not the file's name or content. Each file/directory gets a unique inode number, acting as its identifier, with hard links sharing the same inode. Filesystems have a limited number of inodes, so running out can prevent new file creation, even with free disk space.

A hard link in Linux is an additional filename (or directory entry) that points directly to the same underlying data (inode) on a file system.
A symbolic link (or symlink, soft link) in Linux is a special type of file that serves as a pointer or shortcut to another file or directory, similar to a shortcut in Windows.

Special files - kernel objects represented as file. Symbolic (bytes stream) and blocks (bytes array) devices. 

A sector is the smallest physically addressable unit on a block device. It typically has a size such as 512 bytes or 4096 bytes (a power of two).
A block is the smallest logically addressable unit used by a filesystem. Its size usually corresponds to an integer number of sectors.

Process - an instance of a program in execution, with its own address space. Process has id - PID and associated with system resources. Process consist of one or several thread. Thread is a code running abstraction a schedulable execution context (PC/registers/stack).

Processes have a hierarchical organization (a process tree). The first user-space process is init, which has PID 1 (on most modern Linux systems this is usually systemd). New processes are typically created by calling the fork() system call. The process that calls fork() is the parent, and the newly created copy is the child. In general, all user-space processes are descendants of PID 1.

Every process has real and effective user IDs (UIDs) and group IDs (GIDs), which the kernel uses for permission checks.

Every file has an owner (user), a group, and permission bits that determine access rights for the owner, the group, and others.

Signals are a mechanism for asynchronous notification. A signal is a message delivered to a process to notify it about an event. Signals can be sent by the kernel, by other processes, or by the process itself. Signals can trigger a default action, be ignored, or be handled by a signal handler.
