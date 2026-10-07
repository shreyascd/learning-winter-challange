# Cheatsheet - OS, kernel, processes

## Layers
`Applications -> System calls -> Kernel -> Drivers -> Hardware`

## Key terms
| Term | Meaning |
|---|---|
| Kernel | privileged core of the OS |
| System call | how a program requests a kernel service |
| Process | running program with own memory + PID |
| Thread | execution path inside a process |
| Scheduler | picks which process runs next |
| Context switch | save one process state, load another |
| Daemon/service | background process |
| Virtual memory | per-process view of memory mapped to RAM |

## Linux process commands
```bash
ps aux                  # all processes
ps -ef --forest         # process tree (parent/child)
top / htop              # live view
pstree -p               # tree with PIDs
kill <pid>              # ask a process to stop (SIGTERM)
kill -9 <pid>           # force kill (SIGKILL)
uname -a                # kernel version
cat /etc/os-release     # distro info
lsmod                   # loaded kernel modules
```

## Windows process commands
```powershell
Get-Process
tasklist
taskkill /PID <pid> /F
systeminfo
```

## Kernel types
Monolithic (Linux) | Microkernel (minimal, e.g. QNX/Minix) | Hybrid (Windows NT, macOS XNU)

## Remember
- User space cannot touch hardware directly; it must use system calls.
- PID 1 on Linux = systemd/init.
- Odd parent-child process relations = investigate.
