# Cheatsheet - Verify your VM and CLI setup

## Inside a Linux VM
```bash
uname -a                       # kernel version and architecture
cat /etc/os-release            # distro name and version
systemd-detect-virt            # prints the virtualisation type (e.g. oracle = VirtualBox)
lscpu | head -20               # CPU info
free -h                        # RAM
lsblk                          # disks and partitions
ip addr show                   # network adapters and addresses
```

## Inside a Windows VM (PowerShell)
```powershell
systeminfo | findstr /B /C:"OS Name" /C:"System Type"
Get-ComputerInfo | Select-Object OsName, CsSystemType
Get-NetIPAddress -AddressFamily IPv4
Get-NetAdapter
```

## Host checks
```bash
[ -d /sys/firmware/efi ] && echo UEFI || echo BIOS     # Linux host boot mode
VBoxManage --version                                    # VirtualBox version
VBoxManage list vms                                     # all VMs
VBoxManage list hostonlyifs                             # host-only networks
VBoxManage snapshot "<vm-name>" list                    # snapshots of one VM
```

## Git and the repo
```bash
git --version
git config user.name
git config user.email
git remote -v                       # where pushes go
git log --oneline -5                # recent commits
git status -sb                      # branch and uncommitted changes
```

## Remember
- A README with real command output beats a README with claims.
- Redact tokens, passwords and private IPs before committing screenshots.
