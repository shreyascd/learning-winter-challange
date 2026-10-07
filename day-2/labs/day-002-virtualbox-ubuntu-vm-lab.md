# Lab - Day 002: Install VirtualBox and create an Ubuntu VM

## Goal
Run Ubuntu inside VirtualBox so I have a safe Linux lab for the SOC roadmap.

## Steps
1. Download VirtualBox from virtualbox.org and install it (also the Extension Pack if needed).
2. Download the Ubuntu Desktop (LTS) ISO from ubuntu.com.
3. In VirtualBox: **New** -> name `ubuntu-lab`, type Linux, version Ubuntu (64-bit), pick the ISO.
4. Recommended resources: 4 GB RAM (2 GB minimum), 2 CPUs, 25-30 GB dynamically allocated disk.
5. Start the VM, run the Ubuntu installer, create a user, restart.
6. Install Guest Additions (better screen, clipboard): `sudo apt update && sudo apt install -y build-essential dkms linux-headers-$(uname -r)` then Devices -> Insert Guest Additions CD.
7. Take a **snapshot** called `clean-install` before experimenting.

## Commands to run inside the VM
```bash
uname -a
cat /etc/os-release
ps aux | head -15
pstree -p | head -20
top -b -n 1 | head -15
free -h
lsblk
```

## My output
```
(paste real output here)
```

## Screenshots to add
- [ ] VirtualBox VM settings page
- [ ] Ubuntu desktop running
- [ ] `ps aux` / `pstree` output

## Notes
- Did virtualization (VT-x / AMD-V) need to be turned on in BIOS/UEFI?
- Which process had PID 1 on my VM?
