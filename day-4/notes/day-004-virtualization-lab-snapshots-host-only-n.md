# Day 004 - Virtualization lab: snapshots, host-only networking

Phase 1 - Foundation - Computers & Networks | W01 - D4 | Fri 09 Oct 2026

## What virtualization is
Virtualization runs one or more virtual machines (VMs) on a physical host. Each VM has its own virtual CPU, RAM, disk and network card, so it behaves like a separate computer.
- **Type 1 (bare-metal) hypervisor** - runs directly on the hardware. Examples: VMware ESXi, Microsoft Hyper-V (server), Xen, KVM.
- **Type 2 (hosted) hypervisor** - runs as an app on a normal OS. Examples: VirtualBox, VMware Workstation.
- Virtualization needs hardware support (Intel VT-x or AMD-V), usually enabled in BIOS/UEFI, which is why I checked firmware on Day 1.

## Snapshots
A snapshot freezes a VM's state (disk, and optionally memory) at a point in time. You can roll back to it later.
- Taking a snapshot does not copy the whole disk. New writes go to a separate "differencing" file, so snapshots grow over time.
- **A snapshot is not a backup.** It usually lives on the same disk, so a disk failure loses both.
- Deleting a snapshot merges its changes back into the disk. This can take a while and needs free space.
- Security use: snapshot a clean install, run something risky, then roll back to the clean state.

## Host-only networking
VirtualBox offers several network modes for a VM's adapter:
- **NAT** - the VM reaches the internet through the host; other machines can't reach it directly.
- **Bridged** - the VM sits on the real network with its own IP. Risky for malware work.
- **Host-only** - the VM talks only to the host and to other VMs on the same host-only network. No internet unless a second adapter is added.
- **Internal network** - VMs talk only to each other.

For malware or attack practice, host-only (or internal) keeps the lab isolated from the home or college network.

## Windows evaluation VM
Microsoft publishes free evaluation ISOs on its Evaluation Center. These run fully but have a time limit (typically 90 days), after which they need a proper licence. They are fine for lab use.

## Safe-lab checklist
- Host-only network only for risky work.
- Turn off shared folders and drag-and-drop/clipboard sharing when analysing malware.
- Snapshot before every risky step.
- Never connect an infected VM to bridged networking.

## Questions to revisit
- How do VirtualBox differencing disks store changes after a snapshot?
- What exactly does the host-only adapter's DHCP server hand out?
