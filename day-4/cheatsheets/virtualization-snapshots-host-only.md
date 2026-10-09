# Cheatsheet - Virtualization, snapshots, host-only networking

## Hypervisors
| Type | Runs on | Examples |
|---|---|---|
| Type 1 (bare-metal) | hardware directly | ESXi, Hyper-V server, Xen, KVM |
| Type 2 (hosted) | an existing OS | VirtualBox, VMware Workstation |

## VirtualBox network modes
| Mode | VM reaches internet | Host can reach VM | Other VMs |
|---|---|---|---|
| NAT | yes (via host) | no (no inbound) | no |
| Bridged | yes (own IP) | yes | yes |
| Host-only | no (unless 2nd adapter) | yes | yes |
| Internal | no | no | yes (same network only) |

Host-only network: Network Manager (under Tools in the VirtualBox window) to create or check it.

## Snapshot rules
- Snapshot = point-in-time state, not a backup.
- Snapshots grow over time (differencing files).
- Deleting a snapshot merges data back; check free disk space first.

## Commands inside the Windows VM (cmd / PowerShell)
```powershell
ipconfig /all                       # IP, gateway, DHCP server, adapter info
ping <host-only-gateway-ip>         # reach the host
systeminfo | findstr /B /C:"OS Name" /C:"System Type"
Get-NetAdapter                      # adapters and link status
Get-ComputerInfo | Select-Object OsName, CsSystemType
```

## Commands from the Linux host
```bash
ip addr show vboxnet0               # host-only adapter on the host
VBoxManage list hostonlyifs         # list host-only networks
VBoxManage snapshot "win-eval" list # list snapshots of a VM
VBoxManage snapshot "win-eval" take clean-install
VBoxManage snapshot "win-eval" restore clean-install
```

## Remember
- Host-only + no shared folders = safer lab.
- Snapshot before risky steps, not after.
- Evaluation Windows is time-limited; plan for that.
