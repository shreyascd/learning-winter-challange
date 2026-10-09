# Lab - Day 004: Windows eval VM, first snapshot, host-only network

## Steps
1. Download a Windows evaluation ISO from Microsoft's Evaluation Center (choose Enterprise evaluation, 64-bit).
2. In VirtualBox: **New** -> name `win-eval`, type Microsoft Windows, version Windows 10/11 (64-bit), pick the ISO.
3. Recommended resources: 4 GB RAM, 2 CPUs, 50 GB dynamically allocated disk. Enable EFI if the installer asks for it.
4. Finish the Windows install, then install VirtualBox Guest Additions from the Devices menu (optional).
5. Add a **second adapter**: VM settings -> Network -> Adapter 2 -> Attached to: Host-only Adapter. Create the host-only network in Network Manager if none exists.
6. Keep Adapter 1 as NAT only if you need internet for updates; turn it off afterwards for isolated work.
7. Once the install is clean and updates are done, shut the VM down and take the first snapshot named `clean-install` (VM -> Snapshots -> Take).

## Commands inside the Windows VM
```powershell
ipconfig /all
Get-NetAdapter
ping <host-only-gateway-ip>
```

## Commands on the host
```bash
VBoxManage list hostonlyifs
VBoxManage snapshot "win-eval" list
```

## My output
```
(paste real output here)
```

## Screenshots to add
- [ ] VM Network settings with Host-only Adapter attached
- [ ] Snapshot list showing `clean-install`
- [ ] `ipconfig /all` output inside the VM

## Notes
- Did the host-only adapter give the VM an address in a private range?
- How much disk space did the first snapshot use?
