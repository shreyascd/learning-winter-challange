# Learning Winter Challenge - Lab setup

> Status: **in progress.** Fill in every `TODO` with real values from my own machine before calling this done.

## Summary
A learning log for cybersecurity fundamentals, one folder per day (`day-N/`) with notes, cheatsheets, flashcards, labs and a daily log. This README describes the lab environment those labs run in.

## Host machine
| Item | Value |
|---|---|
| Host OS | TODO |
| CPU | TODO |
| RAM | TODO |
| Disk | TODO |
| Virtualization (VT-x / AMD-V) enabled | TODO yes/no |
| Boot mode (BIOS or UEFI) | TODO |

## Hypervisor
- **VirtualBox version:** TODO (`VBoxManage --version`)

## Virtual machines
| VM name | OS | RAM | CPUs | Disk | Adapter 1 | Adapter 2 |
|---|---|---|---|---|---|---|
| ubuntu-lab | Ubuntu LTS | TODO | TODO | TODO | TODO | TODO |
| win-eval | Windows evaluation | TODO | TODO | TODO | TODO | TODO |

## Snapshots
- `clean-install` on `win-eval`: TODO date taken and what it contains.
- Snapshot list output: paste from `VBoxManage snapshot "win-eval" list`.

## Networking
- Host-only network name and address range: TODO (`VBoxManage list hostonlyifs`).
- Rule I follow: risky work only on host-only or internal networks.

## CLI setup
- Shells used: bash (Ubuntu), PowerShell and cmd (Windows).
- Git version: TODO (`git --version`).
- Editor: TODO.

## Verification
Commands I ran to confirm the setup works (paste real output, redact private IPs and tokens):

```
TODO: output of uname -a / systemd-detect-virt inside ubuntu-lab
TODO: output of systeminfo | findstr inside win-eval
TODO: output of ping between the VM and the host on the host-only network
```

## Screenshots
Add screenshots to `day-7/labs/screenshots/` and link them here:
- [ ] TODO: VirtualBox VM list
- [ ] TODO: Network settings with host-only adapter
- [ ] TODO: Snapshot list for win-eval
- [ ] TODO: Terminal showing git status and log for this repo

## Known issues and what I would change
- TODO

## Week 1 topics covered
Boot chain, OS and kernel, file systems and paths, virtualization and snapshots, command line, binary and encodings. See `day-1/` to `day-6/`.
