# Day 002 - Operating systems: kernel, processes; Windows vs Linux vs macOS

Phase 1 - Foundation - Computers & Networks | W01 - D2

## What an OS does
The operating system sits between applications and hardware. It shares the CPU, RAM, disk and devices between many programs safely and gives each program a simple view of the machine.
Main jobs: process management, memory management, file systems, device drivers, security/permissions, and a user interface (shell or desktop).

## Kernel
The kernel is the core of the OS and runs with full hardware privileges.
- **Kernel space** - privileged mode (ring 0). Can touch any memory or device.
- **User space** - where normal programs run (ring 3). Limited access.
- Programs ask the kernel for services through **system calls** (open a file, create a process, send network data). This boundary is what keeps one buggy or malicious program from crashing or reading everything else.
- Kernel types: **monolithic** (Linux: most services inside the kernel, fast), **microkernel** (minimal kernel, services outside, more isolated), **hybrid** (Windows NT, macOS XNU: a mix).

## Processes and threads
- A **program** is a file on disk. A **process** is a running instance with its own memory, open files and a process ID (PID).
- A **thread** is a unit of execution inside a process; threads of one process share its memory.
- Process states: new, ready, running, waiting (blocked), terminated.
- The **scheduler** decides which ready process gets the CPU next, switching quickly (context switch) so many things seem to run at once.
- Processes get created by a parent (`fork`/`exec` on Linux, `CreateProcess` on Windows). PID 1 on Linux is init/systemd, the ancestor of everything.
- A **daemon/service** is a background process with no user interface.

## Memory management basics
Each process gets its own **virtual address space**. The OS and CPU map it to real RAM pages, so processes can't read each other's memory. When RAM is short, pages can be swapped out to disk.

## Windows vs Linux vs macOS
| | Windows | Linux | macOS |
|---|---|---|---|
| Kernel | NT (hybrid) | Linux (monolithic) | XNU (hybrid, Unix-based) |
| Source | closed | open source | mostly closed, Darwin core open |
| File system | NTFS | ext4, xfs, btrfs | APFS |
| Shell | PowerShell, cmd | bash, zsh | zsh |
| Package tools | installers, winget | apt, dnf, pacman | Homebrew, App Store |
| Typical use | desktops, corporate PCs | servers, cloud, security tools | creative work, developers |
| Security note | biggest malware target | fewer desktop threats, but runs most servers | Gatekeeper, SIP, notarisation |

## Why this matters for security
- Privilege separation (user vs kernel, normal user vs admin/root) is the base of OS security.
- Malware often tries **privilege escalation** to reach kernel level or admin.
- Analysts need to read process lists on every OS: unknown parent/child relations and odd process names are common red flags.
- Linux is the main environment for most security tools (Kali, SIEM servers), so being comfortable in it matters.

## Questions to revisit
- How exactly does a context switch save and restore state?
- What is the difference between a rootkit in user space vs kernel space?
